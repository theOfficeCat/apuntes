MIPS es una arquitectura RISC como ya se ha comentado antes y, por tanto, a diferencia de algunas arquitecturas CISC no permite el uso de accesos a memoria en las mismas operaciones de cálculo.

Las instrucciones se pueden dividir en varios grupos:

## Operadores

### Operadores en modo de registro

Todos los operadores se encuentran en registro y se escribe de forma que el primero es el de destino y los demás son los operandos.

Ejemplo:
```asm
add   rs, ra, rb
addu  rs, ra, rb
```

### Operadores con inmediato

La instrucción contiene dos registros para operar siendo uno el destino y otro un operando y un inmediato de 16 bits.