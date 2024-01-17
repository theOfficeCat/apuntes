El usuario ve lo que se llama como Virtual File System. Tienes las syscalls y las diferentes tablas del sistema de ficheros.

El VFS tiene los drivers de los diferentes sistemas de ficheros o servicios que ofrece el VFS.

Estos ficheros pasan a una buffer cache en las peticiones de disco. En caso de no encontrar el dato en la cache se pasa a la petición al disco. Esta cache además también traduce de bloque a sector de disco.

Por debajo de esta están ya los drivers de manejo de hardware del disco.


```
+---------------------+
| Virtual File system |
+---------------------+
 |         |         |
EXT2      NTFS     PIPES
 |         |         |
+---------------------+
| Buffer cache        |
+---------------------+
    |             |
+--------+    +--------+
| Driver |    | Driver |
+--------+    +--------+
    |             |
  (---)         (---)
  (   )         (   )
  (---)         (---)
```

El VFS tiene lo que se llama como Virtual I-nodes. que contiene un i-nodo a la estructura específica del sistema de ficheros.

## Gestor

El VFS tiene su propio gestor para encargarse de ir bloqueando los procesos en las peticiones al no saber si van a ser de alta o baja latencia.

Para permitir mayor paralelismo este gestor de VFS tira a los gestores de los sistemas de ficheros específicos en caso de que hayan. Estos pasarán las peticiones a un gestor de la buffer cache.