## Latencia y ancho de banda

La latencia es el tiempo que pasa entre la solicitud de un dato a memoria y el tiempo qeu tarda esta en devolver el dato a la unidad de proceso.

El ancho de banda es la cantidad de datos que se pueden transmitir por unidad de tiempo.

## Localidad

La memoria tiene una propiedad que es la localidad, dividida entre localidad espacial y temporal.

### Localidad espacial

Al acceder a un dato en una posición en específico es muy probable que pronto se acceda a un dato en una posición contigua.

### Localidad temporal

Si se accede a un elemento en específico es posible que se acceda de nuevo a esta.

## Jerarquía de memoria

La memoria se divide en diferentes en base a una jerarquía donde hay una mayor velocidad de acceso al dato por velocidad de la memoria o por distancia a recorrer del dato.

## Tiempo de acceso a memoria

Todos los accesos a memoria tienen una latencia mímina de $c_{acierto}$ ya que siempre hay que acceder a la caché para ver si el dato está o no, provocando un hit o un miss.
$$CMA = c_{acierto} + f_R \cdot P_f$$
Con $c_{acierto}$ la latencia en caso de acierto, $f_R$ es la tasa de fallos ($\frac{fallos}{accesos totales}$) y $P_f$ es la latencia en caso de fallo.

## Mejora de rendimiento (concurrencia)

### Segmentación

La ejecución del procesador está dividido en varias etapas y donde una vez que una instrucción ha pasado por una etapa ya no vuelve a esta. Tiene un $CPI$ ideal de 1.

### Paralelismo

Se ejecutan a la vez diferentes instrucciones, replicando etapas. Tiene un $CPI$ ideal $<$ 1.

### Multihilo

Ejecución concurrente a nivel de hilo de procesado.

