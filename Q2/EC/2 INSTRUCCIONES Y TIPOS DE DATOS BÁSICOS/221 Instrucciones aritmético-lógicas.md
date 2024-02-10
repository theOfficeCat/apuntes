Las intrucciones de operaciones aritmético-lógicas se pueden dividir en dos grupos:
- Operaciones con signo
- Operaciones sin signo

Para poder identificarlas se puede ver en el nombre de la operación donde si contiene una u al final es que es una operación sin signo.

### Modo de registro

Todos los operadores se encuentran en registro y se escribe de forma que el primero es el de destino y los demás son los operandos.

Ejemplo:
```asm
add   rs, ra, rb
addu  rs, ra, rb
```

### Modo de inmediato

La instrucción contiene dos registros para operar siendo uno el destino y otro un operando y un inmediato de 16 bits con el que se realiza extensión de signo en caso de ser operaciones con signo o rellenando con 0 en caso de no.

Los nombres de estas instrucciones contienen una i al final.

Ejemplo:
```asm
addiu rs, ra, 16
ori   rs, ra, 0x5678
lui   rs, 0x1234
```

Hay que fijarse en la operación lui que no es como tal una operación aritmético lógica sino que se trata de cargar en un registro en la parte alta un valor (lui -> load upper immediate) y deja la mitad baja del registro a 0. De esta manera la instrucción del ejemplo dejaría en el registro de destino el valor `0x12340000`.