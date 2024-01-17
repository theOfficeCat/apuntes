El gestor va a tener un semáforo para controlar que no se tenga un bucle infinito consumiendo toda la CPU. Este semáforo empezará bloqueado.

```C
sem_gestor <- 0

while (1)
{
	sem_wait(&sem_gestor);
	coger_peticion();
	// Hacer I/O
	q_ioend_add();
	sem_post(&sem_op);
	
}
```

## Envío de datos al gestor

Se tiene una cola de petición de entrada/salida `q_iorb`. Cada bloque contiene los parámetros necesarios para realizar la operación.

- tipo de operación
- datos dependientes de la operación
- semáforo de la operación

Además estas colas necesitan sus propias colas para evitar que en procesadores multiprocesador hayan problemas de escritura o lectura simultánea.

```C
sem_qiorb <- 1
sem_op <- 0

read_dep()
{
	sem_wait(&sem_qiorb);
	encolar_peticion(); // configura el union de b_iorb;
	sem_post(&sem_qiorb);
	sem_post(&sem_gestor);
	
	sem_wait(&sem_op);
	sem_wait(&sem_qioend);
	get_result(q_ioend);
	sem_post(&sem_qioend);
	
}
```

## Envío de datos del gestor

Se tiene otra cola `q_ioend` a la que se van añadiendo los resultados de la entrada/salida

```C
sem_qioend <- 1
sem_op <- 0
```