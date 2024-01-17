
## Throughput

Se ejecutan diferentes programas seriales no relacionados entre sí en diferentes procesadores. De esta manera en la forma más simple una cantidad $k$ de programas en $P$ procesadores se realizaría una asignación de $\frac{P}{k}$ procesadores para cada programa.

## Computación paralela

### Concurrencia

Se divide un problema en diferentes tareas. Para asegurar la correcta ejecución paralela hay que asegurar que cada tarea serial se ejecuta en un único procesador y que múltiples tareas se van turnando en el procesador, de forma que el tiempo de ejecución se multiplexa en diferentes tareas. Esta tarea se asigna al sistema operativo.

### Paralelismo

Se usa para reducir el tiempo de ejecución de un único programa, donde múltiples procesadores ejecutan de forma simultánea las diferentes tareas concurrentes.