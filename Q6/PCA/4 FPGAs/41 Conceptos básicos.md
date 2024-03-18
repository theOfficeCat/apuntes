No vamos a usar HDL, la programación se va a hacer a través de pragmas usando OmpSs.

- Los tamaños tienen que ser constantes.
- Si se quiere usar lo mismo en varios aceleradores mejor usar includes.

## Copia de datos

Al hacer copy_in se copia en unas páginas pinneadas del espacio de kernel y a las que accede el acelerador a través de DMA para la copia de los datos de entrada y de salida.
