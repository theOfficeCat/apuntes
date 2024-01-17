## Tiempo de ejecución

$$
T = N \cdot CPI \cdot t_c$$
siendo $T$ el tiempo de ejecución, $N$ el número de instrucciones, $CPI$ las instrucciones por segundo y $t_c$ el tiempo de ciclo ($\frac{1}{frecuencia}$)

El rendimiento se calcula con
$$R = \frac{1}{T}$$
## CPI

El CPI es la suma ponderada por instrucciones del CPI individual de cada tipo de instrucción.
$$CPI = \sum_{i = n}^n{\frac{N_i \cdot CPI_i}{N}} = \sum_{i = 1}^n{f_i \cdot CPI_i}$$
Siendo $N_i$ número de instrucciones del tipo $i$, $N$ el número de instrucciones totales, $CPI_i$ el CPI de las instrucciones del tipo $i$ y $f_i$ el factor de instrucciones del tipo $i$ respecto al total ($\frac{N_i}{N}$)

## MIPS

Son las millones de instrucciones por segundo. Esto solo se puede comparar con sentido si se utiliza el mismo ISA porque si no se están comparando instrucciones diferentes

$$MIPS = \frac{N}{T} = \frac{N}{N \cdot CPI \cdot t_c} = \frac{f}{CPI}$$
## Speed-up

Es la mejora en rendimiento de un programa.

$$speed\text{-}up = \frac{Tiempo\text{ }original}{Tiempo\text{ }con\text{ }la\text{ }mejora}$$
### Ley de Amdahl

Parametriza la mejora en función de $f_m$ el porcentaje del tiempo en el que se aplica la mejora y $g_m$ ganancia de la mejora cuando se aplica, con la función:

$$ganacia = \frac{1}{(1-f_m) + \frac{f_m}{g_m}}$$
## slow-down

$$slow\text{-}down = \frac{(Tiempo\text{ }original - Tiempo\text{ }nuevo)}{Tiempo\text{ }original}$$

## Energía y potencia

$$Potencia = \frac{Energía}{Tiempo}$$
La energía y la potencia tienen 3 componentes:
- Conmutación (dinámico)
- Corriente de fuga (estático)
- Corriente de cortocircuito (estático)

Es importante tomar en cuenta que a mayor consumo se consume más corriente y además la temperatura es más alta.

### Potencia

#### Conmutación

$$P_{conmutación} = C \cdot V^2 \cdot f$$
#### Corriente de fuga
$$P_{fuga} = V \cdot I_{fuga}$$
#### Corriente de cortocircuito
$$P_{cc} = t_{cc} \cdot I_{pico} \cdot P_{0 \rightarrow 1} \cdot f$$
Siendo $t_{cc}$ el tiempo de cortocircuito en cada transición de 0 a 1 y $P_{0 \rightarrow 1}$ la probabilidad de paso de 0 a 1.

### Energía

Es importante tenerla en cuenta por la duración de las baterías y la factura eléctrica.

$Energía = Intensidad \cdot Tiempo \cdot Voltaje$

## Eficiencia energética

Sirve para medir el rendimiento que se obtiene por cada $W$.

| Gama de bajo consumo | Gama media | Gama de alto rendimiento |
|-|-|-|
|$\frac{MIPS}{W}$|$\frac{MIPS^2}{W}$|$\frac{MIPS^3}{W}$|
