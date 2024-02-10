la arquitectura MIPS solo permite el acceso a memoria en las instrucciones específicamente definidas para ello.

Estas instrucciones se dividen en dos conjuntos: las instrucciones de carga o de almacenado en memoria.

Se basan en tener un registro del que se lee el valor en instrucciones load o en el que se escribe en instrucciones store, otro registro donde se almacena una dirección de memoria más un inmediato de 16 bits que se le suma la dirección almacenada en registro.

## Accesos de 4 bytes

Estas instrucciones requieren que la dirección resultado de la suma del valor del registro de la dirección con el offset sea múltiplo de 4.

```asm
lw rb, off16(ra)
sw rs, off16(ra)
```

## Accesos de 2 bytes

Estas instrucciones al igual que las anteriores requieren que la dirección que queda de la suma sea múltiplo en este caso de 2. Además