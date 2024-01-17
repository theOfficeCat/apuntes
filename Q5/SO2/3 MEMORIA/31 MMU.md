## MMU (Memory Management Unit)

Servía para evitar el acceso a las posiciones de memoria del SO.

Se ponía la primera posición de memoria donde se almacena el sistema operativo, de forma que en caso de que se quisiera acceder a una posición de memoria mayor o igual a esta dirección se bloqueara el acceso en modo usuario.

Después se pasó a usar para guardar la posición inicial del proceso, usándose como posición base para calcular la posición física del acceso que se quiera hacer.

En esta situación la MMU pasa a tener 2 registros:

- Dirección física
- Tamaño en memoria del proceso

### Fragmentación

Esto puede provocar el problema de tener los procesos dispersados por la memoria física, provocando fragmentación e impidiendo que nuevos procesos se puedan generar por no tener espacio consecutivo disponible.

Con esto se hace una desfragmentación de memoria moviendo los procesos.

Esta desfragmentación cuando los procesos fueron creciendo en tamaño ralentizaban mucho la ejecución. Como solución a esto se hizo que los procesos no vayan consecutivos en memoria. Para esto se crea la TLB [32 TLB](32%20TLB.md).