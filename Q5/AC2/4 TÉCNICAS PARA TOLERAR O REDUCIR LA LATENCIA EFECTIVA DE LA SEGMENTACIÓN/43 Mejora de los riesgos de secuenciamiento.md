## Clasificación de los saltos

| | Condicionales (branch) | Incondicionales (jump) |
|-|-|-|
| Directos (absolutos) | beq R1, R2 | jmp R0 |
| Indirectos (relativos al PC) | beq R1, 1$ | jmp 1$ |

En la asignatura usaremos únicamente saltos indirectos.

El primer diseño es ineficiente ya que en la etapa de ALU se sabe ya si se va a saltar o no, por lo que se puede acortar la ejecución de la instrucción únicamente hasta la etapa ALU.

Para los saltos incondicionales se pude añadir un sumador en la etapa D/L que calcule CP + Inmediato, de forma que se puede tener saltar al salir de D/L.