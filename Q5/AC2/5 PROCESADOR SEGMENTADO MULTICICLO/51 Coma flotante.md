Las instrucciones de coma flotante a nivel de instrucción son similares a las de enteros. Tiene un banco de registros propio.

Las instrucciones de acceso a memoria usan un registro entero (dirección) y de coma flotante (dato).

Estas instrucciones de cálculo en coma flotante son mucho más lentas que las instrucciones de enteros, de forma que tienen varias etapas de ejecución en suma y multiplicación pero en división no, de forma que la suma y multiplicación ocupan 4 etapas con latencia de inicio de 1 y la división ocupa 20 etapas y tiene una latencia de inicio de 20 etapas.

En las instrucciones de salto en lugar de tener una etapa ALU habrá una etapa FEV.