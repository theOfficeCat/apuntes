MIPS es un ensamblador RISC, es decir, con instrucciones de tamaño fijo y simples a diferencia de los ensambladores tipo CISC que son instrucciones de tamaño variable e instrucciones mucho más complejas.

Esta arquitectura (MIPS32) usa 32 registros de 32 bits, palabras de 32 bits, instrucciones y direcciones de 32 bits y memoria de $2^{32}$ bytes accesibles. Se usa una organización de memoria little-endian.

## "Declaración de variables"

En los ensambladores no se pueden declarar variables como sí se puede hacer en lenguajes de más alto nivel. En cambio lo que se puede hacer es el uso de etiquetas que llevan a un espacio de memoria determinado.

Estos espacios se pueden definir de diferentes formas en base al tipo de dato que se quiera guardar:

| nombre | tamaño | dirección |
| ---- | ---- | ---- |
| `.byte` | 1 | - |
| `.half` | 2 | múltiplo de 2 |
| `.word` | 4 | múltiplo de 4 |
| `.dword` | 8 | múltiplo de 8 |

Estos espacios de memoria se alinean de forma automática.

Además de estos se puede declarar un espacio usando `.space`que se usa para declaración de vectores y estructuras grandes y que requieren un alineado explícito con `.align` seguido de $n$ siendo $n$ 1, 2 o 3 que especifica un alineado de $2^n$ bytes.




