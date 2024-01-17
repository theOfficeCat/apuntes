```C
int open(char *path, int flags[, int mode]);
```

Es una de las llamadas a sistema que más tarda en ejecutarse.

Primero pilla el path e intenta acceder al dispositivo lógico en concreto queriendo llegar a i-nodo. Con el i-nodo accede a la tabla de i-nodos del sistema de ficheros (estructura en memoria que guarda los i-nodos que se han abierto). En caso de que esté en la tabla de i-nodos se lee directamente de ahí para evitar el acceso a disco. En caso que no se ejecuta un algoritmo pseudo-LRU para sustituir un i-nodo CERRADO de la tabla por el nuevo.

Obtiene el MAJOR y minor del dispositivo y busca entre los device descriptors uno que tenga el mismo MAJOR y minor. se guarda el puntero del Device Descriptor.

La ejecución de `open()` allocata una nueva entrada en la tabla de ficheros abiertos.

La PCB tiene una tabla de canales que apunta a esta entrada de la tabla de ficheros abiertos.

PCB -> Tabla de Canales -> entrada de la Tabla de Ficheros Abierto -> entrada da la tabla de i-nodos -> device descriptor -> funciones para trabajar con el dispositivo.

El poder tener diferentes veces el mismo i-nodo abierto en la tabla de ficheros abiertos permite un acceso concurrente.

En cambio el tener varias entrada de diferentes o la misma tabla de canales apuntando a una misma entrada de la tabla de ficheros abiertos permite un acceso compartido. Se puede conseguir a través de un fork ya que esto copia la tabla de canales del padre al hijo


## Tabla de i-nodos

campos:
- `*i-nodo`
- `*device_descriptor`
- 

## Tabla de ficheros abiertos

campos:
- `*lectura_escritura`
	- Da el offset con el que se trabaja al escribir o leer en el dispositivo.
- número de referencias