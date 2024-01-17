
La granularidad de una tarea se determina por el tamaño computacional de los nodos del grafo de tareas. De forma que se puede analizar en cuantos nodos se puede dividir una tarea para paralelizarla.

Por ejemplo teniendo un bucle de $N$ iteraciones donde se comprueba una propiedad de un elemento de una base de datos se comprueba que el trabajo de este nodo será de $Nk$ siendo $k$ el tiempo de ejecución de cada iteración, de forma que se puede paralelizar este bucle en $N$ tareas con un trabajo $k$.

Con esto podemos sacar el paralelismo potencial de un procesamiento con esta división en cálculos paralelos.

Además podemos ver que cuanto más se acerca a este "grano fino" en la granulación del procesado mayor paralelismo se obtiene. Aun así está el problema de que el inicializar estas tareas, recibir los datos, etc. requiere también un trabajo extra por lo que la paralelización excesiva puede conllevar un pérdida de eficiencia a si se hiciera algo menos paralelo el procesado.