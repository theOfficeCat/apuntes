Cuando hay una dependencia de datos se puede acortar este tiempo de latencia entre instrucciones permitiendo el paso del valor entre etapas.

Hay dos posibles implementaciones de estos cortocircuitos:

![[tipos_de_implementacion_cortocircuito.png|Las dos implementaciones de cortocircuito]]

En el procesador que estudiamos al tener ALUs rápidas y registros rápidos se usa la segunda porque reduce el impacto en el tiempo de ciclo mucho mejor que la de inicio.

## Análisis

para saber la cantidad de cortocircuitos necesarios hay que analizar las parejas productores-consumidores.