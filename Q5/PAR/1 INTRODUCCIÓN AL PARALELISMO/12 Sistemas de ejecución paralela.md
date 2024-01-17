
Dentro de los sistemas paralelos hay dos grandes grupos en base a la distribución de la memoria.

## Memoria compartida

Toda la memoria es accesible por todas las CPUs a la que acceden desde una red de interconexión que las conecta todas con la memoria y entre sí.

## Memoria distribuida

En esa distribución cada CPU tiene su propia memoria específica, de forma que se bloquea el acceso al resto a esa memoria. Los demás procesadores para acceder a estos datos deben de hacer una petición a la CPU correspodiente a través de la red de interconexión.

---

De forma idea cada CPU debería recibir una porción $\frac{1}{P}$ del programa, de forma que el tiempo de ejecución se reduce en $P$ siendo $P$ la cantidad de procesadores asignados a la ejecución. Por tanto el tiempo de ejecución ideal seguiría la fórmula 
$$T = \frac{\frac{N}{P}}{F} = \frac{N}{P \cdot F}$$
