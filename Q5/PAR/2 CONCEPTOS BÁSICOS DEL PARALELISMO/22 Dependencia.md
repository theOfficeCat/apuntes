
La computación paralela trae también consigo una dependencia que determina el orden necesario de ejecución de las tareas paralelas al haber tareas que dependen de otras.

### Grafo de dependencia de tareas

Esta dependencia se puede mostrar en un grafo de dependencia de tareas, siendo este un grafo acíclico direccionado, donde cada nodo representa una tarea y su peso representa la cantidad de trabajo necesario para realizarla y cada arista una dependencia.

Con este grafo podemos calcular el tiempo de ejecución serial $T_1$ de la siguiente manera:

$$T_1 = \sum^{nodos}_{i = 1}(trabajo\_nodo_i)$$

También podemos calcular el camino crítico, que es el camino en el grafo de tareas con el mayor tiempo de trabajo acumulado

$$T_{\infty} = \sum_{i \in camino\_crítico}(trabajo\_nodo_i)$$
Asumiendo que se tienen suficientes procesadores para ejecutar estos procesos en paralelo al resto de nodos fuera de este camino crítico.

De esta manera se puede calcular la mejora en el tiempo de ejecución (Paralelismo) de este programa con esta simple operación:

$$Paralelismo = \frac{T_1}{T_{\infty}}$$

Además también se tiene $P_{min}$ que representa la cantidad mínima de procesadores para poder ejecutar esta tarea en el tiempo $T_{\infty}$.