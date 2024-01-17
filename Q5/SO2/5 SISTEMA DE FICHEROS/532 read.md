

```C
int read(int fd, char *buff, int size);
```

se entra en sistema

con el fd se accede a la tabla de canales que accede a la tabla de ficheros abiertos. Se obtiene el puntero de escritura/lectura y va a la tabla de i-nodos. Accede al i-nodo y al device descriptor que tiene un puntero a la función `read_driver()`

```C
read_driver(i-nodo, offset, buff, size);
```

## Cosas para que funcione mejor

Cuando el thread pase a la ejecución de la entrada/salida se tiene que bloquear.

Se tiene un [[533 Gestor]] que siempre está en modo sistema que se encarga de las peticiones de entrada/salida.

al hacer la llamada a sistema para la lectura se realiza el proceso normal pero el puntero del device driver apunta al gestor de dispositivo que tiene su propia función `read_dep()`.
