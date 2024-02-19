## Compiladores

### Flags

Hay diferentes flags de optimización:

- O0
- O1
- O2
- O3 (hasta aquí llega gcc pero otros compiladores tienen mayores niveles de optimización)
- O4
- O5
- O6
- Ofast
- Os

Es necesario usar `-march=(arch)` para que añada las optimizaciones para la arquitectura del dispositivo, por ejemplo para usar la arquitectura propia donde se está ejecutando se usa `-march=native`.

Con `-g` se puede añadir información extra como pueden ser las líneas de código.

`-pg` a diferencia se usa para compilar para el análisis de profiling con gprof. [[23 PCA]]

`-I` sirve para marcar el path del que hacer los include.






---

Se puede leer el ensamblador usando el compilador con la flag `-s`. Con la flag `-e` se puede ver el contenido de las macros.
### Otros compiladores

- gcc
- icc
- icx
- xec

## Linker

`-L` para añadir la librería.

`-l` para marcar la librería que se usa.

`-static` crea el binario con todas las librerías dentro. Se permite la ejecución en un sistema de la misma arquitectura que no tenga esas librerías instaladas pero hace un binario mucho más grande, además que no permite el uso de actualizaciones de la librería sin recompilar.