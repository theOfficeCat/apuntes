
```C
void * pthread_create(void* (*func)(void*), void *param) // POSIX
|
v

void *function(void *param)
{
	...

	pthread_exit();
}

void * createThread()   // Windows
```

## Pasos para crear un thread

1. Allocatar TCB
	- Linux: El proceso no existe como tal. No hay ninguna estructura que guarde los datos del proceso, únicamente los TCB (los task_union).
	- Windows: Los procesos existen de forma explícita. Está la estructura KPROCESS que es el PCB del proceso. Se montan las estructuras de forma que dentro del KPROCESS se tiene una lista de los threads que pertenecen al proceso teniendo sus estructuras (KTHREAD).
2. Se asigna el user stack.
3. Se asigna el system stack.
4. Se asigna el TLS en una zona de memoria propia para el thread.
5. INIT CTXT EXEC
	- Linux: Se copian las estructuras de uno a otro con los mismos datos de lo que sería el PCB.
6. Inicializar pilas
	- f
7. Ready queue
	- f


Se crea un wrapper que se ejecute antes de la función que se pasa a pthread_create. Esta función tiene que ejecutar la función que se la pasa por parámetro y después phtread_exit(). De esta forma se asegura que se salga del thread.

```C
void pthread_wrapper(*func, *param)
{
	(*func)(param);
	pthread_exit();
}
```

### System stack cuando se va a crear el thread

- SS
- ESP
- PSW
- CS
- EIP
- CTXT SW
- @ret
- %ebp

Con esto SS.ESP de sistema tiene que apuntar a la cima del stack de usuario y CS.EIP apunta a la dirección de pthread_wrapper.

### User stack cuando se crea el thread

- param
- func
- 0 (dirección de retorno a la que nunca se debería llegar)

## Cambios en task_switch

```C

task_switch(*new)
{
	...
	
	if (current()->PID != new->PID)
	{
		set_cr3();
	}
}

```

Esto evita la ejecución de la línea que retarda más el task_switch en caso de que no sea necesario ejecutarlo.

---> NEXT THREAD
|			SAME PROCESS
|
|---> NEXT PROCESS
			NEXT THREAD

