
> [[021 Componentes]]

Los condensadores no dejan pasar corriente continua.

### Circuito RC

$$Vc = V_I ( 1- e^{-t/RC})$$

$$
V_I = V_R + V_C
$$
$$
V_I = I \cdot R + \frac{Q}{C}
$$

En esta fórmula se conoce tanto R como C al ser valores propios de los
componentes del circuito. Y al ser Q la intensidad por unidad de tiempo
queda que

$$
V_I = \dfrac{\mathrm{d} Q}{\mathrm{d} t} R + \frac{Q}{C}
$$

Al tener una ecuación diferencial de primer grado del tipo

$$
\dfrac{\mathrm{d} Q}{\mathrm{d} t} = ... + ... Q
$$

Esta solo se puede resolver con una exponencial. (las ecuaciones diferenciales
de segundo grado se resuelven con sin o cos)