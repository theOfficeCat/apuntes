Algunos programas pueden repetir alguna computación con los mismos datos de input. Debido a esto y, si el cálculo es costoso, se puede plantear el guardar la información en alguna estructura de datos.

Este tipo de optimizaciones no las puede hacer el compilador.

## Estrategias

### Precómputo

En caso de que sean pocos casos se pueden precalcular todos los casos y guardarlos en un array para el posterior acceso.

### Guardado en cómputo

Se van guardando los datos cuando se van calculando.