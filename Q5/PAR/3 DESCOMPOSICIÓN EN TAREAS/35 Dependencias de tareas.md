Para evitar el uso de barreras se puede hacer un control de las dependencias al declarar las tareas a través de:

```
#pragma omp task [depend (in : var_list)]
				 [depend (out : var_list)]
				 [depend (inout : var_list)]
```

pudiendo incluir secciones de arrays en la lista de variables a través de `v[0:n]` por ejemplo.

El problema de usar barreras es que generan una serialización evitable.