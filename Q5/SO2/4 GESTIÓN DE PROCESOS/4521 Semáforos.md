Para evitar conflictos se tiene una estructura de semáforo que bloquea los threads que quieren ejecutarse y el semáforo "está en rojo".

```C

struct sem_t
{
	int count;
	list_head blocked;
}

int sem_init(sem_t *s, int initial)
{
	s->count = initial;
	INIT_LIST_HEAD(s->blocked);
}

int sem_wait(sem_t *s)
{
	s->count--;
	if (s->count < 0)
	{
		block(current(), s->blocked); // list_add; sched_next;
	}
}

int sem_post(sem_t *s) // sem_signal
{
	s->count++;
	if (s->count <= 0)
	{
		unblock(s->blocked); // list_first; lis_del; list_add(ready_queue);
	}
}
```


Ejemplo de uso:

T1

```C
sem_wait(&s);
i[pos] = N1;
pos++;
sem_post(&s);
```

T2

```C
sem_wait(&s);
i[pos] = N2;
pos++;
sem_post(&s);
```

## Semáforos de sincronización

Se pueden usar los semáforos para sincronizar los threads.


Común
```C
sem_t s;
sem_init(&s, 0);
```

T1
```C
rellenar_matriz();
sem_signal(&s);
```

T2
```C
sem_wait(&s);
consumir_matriz();
```

## Semáforos de recursos

Común
```C
sem_t s;
sem_init(&s, 2);
```

T1
```C
sem_wait(&s);
imprimir();
sem_signal(&s);
```

T2
```C
sem_wait(&s);
imprimir();
sem_signal(&s);
```

T3
```C
sem_wait(&s);
imprimir();
sem_signal(&s);
```

