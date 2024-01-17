## Programadores

Dispsitivo externo al chip que graba el programa en la memoria interna de este a través de unos pines en específico.

## OTP

Memoria de escritura única que se usa para grandes tiradas de chips. Los programa el propio fabricante y puede quemar los pins de escritura del programa para evitar también la lectura y la copia del código.

## Bootloader

Una primera parte del programa fija que recibe por línea serie el programa y lo copia en la memoria y finalmente hace el jmp a la primera instrucción de este. Tiene que rehacer los saltos, las interrupciones se llaman desde 