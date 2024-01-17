
Un caso donde la computación paralela ayuda es para acelerar el procesamiento de datos repetitivos.

Por ejemplo ante la necesidad de hacer una comprobación en una base de datos contando la cantidad de elementos que cumplen una determinada condición se puede hacer de dos formas:

- Serial: un for loop recorriendo la totalidad de la base de datos comprobando uno a uno el parámetro.
- Paralelo: dividir la ejecución en múltiples tareas, por ejemplo 4, y hacer este for loop más corto, teniendo al final que sumar cada contados individual de cada tarea para obtener la cantidad final.

En el segundo caso de forma ideal se tendría un tiempo de ejecución de 

$$T_P = \frac{T_S}{P}$$
Siendo $T_P$ el tiempo de ejecución paralela, $T_S$ el tiempo de ejecución serial y $P$ la cantidad de procesadores que se usan.

Aun así a esto se le tiene que agregar un tiempo adicional necesario para la unificación de este dato calculado paralelamente, lo que daría una fórmula

$$T_P = \frac{T_S}{P} + T_{ovh}(P)$$
Siendo $T_{ovh}$ el tiempo necesario para obtener el dato y agregarlo a la suma conjunta.
