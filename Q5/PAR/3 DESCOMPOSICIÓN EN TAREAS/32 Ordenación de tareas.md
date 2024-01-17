Para sincronizar tareas se pueden usar las diferentes barreras que existen:

```C
#pragma imp barrier
```
y las barreras implícitas al final de los constructores de OpenMP esperan a que acaben todos los hilos.

```C
#pragma omp taskwait
```

Espera a que acaben todos los hijos de la tarea pero no los hijos de esta

```C
#pragma omp taskgroup
```

Espera a que acaben todos los hijos y los descendientes de estos de la última tarea.