funciona a partir de tareas que se pueden ejecutar de forma paralela si no tienen dependencias entre sí. Permite el manejo de fallos de tareas y excepciones.

Se despliega en una arquitectura de master-worker.

## Creación de tareas

```Python
@task(returns=int)
def tarea():
	...
```

Las tareas se crean usando un decorador `@task` y añadiendo el tipo que se devuelve.

```Python
@task(returns=int, dato=)
```


### Limitación de nodos de ejecución

Se puede añadir un decorador para marcar esta limitación.

```Python
@constraint(computation_nodes=1)
@task()
```