```C
#pragma omp parallel
```

Genera una tarea implícita por cada hilo en el equipo y se ejecuta de forma inmediata.

A través de varias funciones se puede acceder a datos generados por la creación de estas tareas:

```C
int omp__get_num_threads() // Devuelve la cantidad de hilos que se están usando

int omp_get_thread_num() // Devuelve el indentificador del hilo que se está usando
```

```C
#pragma omp task
```

Genera una tarea explícita empaquetando código y datos

```C
#pragma omp taskloop
```

Genera varias tareas explícita para bloques de iteraciones de un bucle, con una sincronización `taskgroup`  al final del bucle.

En ambos casos esto se define dentro de una región marcada por el `parallel`.

