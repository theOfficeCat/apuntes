Si se tuvieran registros infinitos los WAR y WAW desaparecerían. Esto es debido al tamaño de instrucción que permiten una cantidad específica de registros.

Ya el compilador intenta usar todos los registros posibles para evitar las dependencias o que estén lo más alejadas posibles. Además hay una optimización a nivel de hardware que traduce de registros lógicos (1..32) a registros físicos (1..N) N = 64, 128, 256, ...

Otra técnica es el desenrolle de bucles que se basa en replicar varias veces el contenido de un bucle para para iterar menos veces.