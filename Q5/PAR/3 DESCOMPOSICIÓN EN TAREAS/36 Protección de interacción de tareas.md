Para evitar interacción entre tareas se pueden usar dos mecanismos:


## Accesos atómicos

Garantiza la atomicidad en instrucciones de escritura y lectura

```C
#pragma omp atomic
expression
```

## Exclusión mutua

Mecanismo que asegura que solo una tarea a la vez ejecuta una región crítica

```C
#pragma omp critical
{
	...
}
```

