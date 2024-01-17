Primer funcionamiento:

|nombre|F/D|metadatos|
|-|-|-|
|a.b|F|(mucha cosa)|

Para evitar rutas absolutas enormes se pasa de una organización de árbol a grafo.

Este sistema de grafo provoca problemas como la múltiple referencia a un archivo desde diferentes rutas que con una eliminación del fichero puede causar conflictos.

Solución:

> i-nodos: separar el nombre del fichero respecto a sus datos asociados.
>
> Se guarda la cantidad de referencias que tiene el i-nodo para saber cuando se tiene que eliminar.

Datos que contiene el i-nodo:

- \# referencias
- metadatos
- MAJOR
- minor

## Directorio

Es un conjunto de hard-links (pareja de nombre de fichero e i-nodo)