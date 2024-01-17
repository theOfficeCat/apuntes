El conjunto de Mandelbrot es el conjunto de números complejos $p$ en un representación 2D que la secuencia

$$z_{n+1} = z_n^2+p$$
siempre cumpla

$$ \forall_{n}(\lvert z_n \rvert \lt 2) $$
ya que se sabe que todo punto con una distancia mayor de 2 al origen no pertenece al conjunto.

Se limita la ejecución de este algoritmo para comprobarlo con una cantidad máxima de pasos que aunque no es totalmente exacto facilita la ejecución.

Como es razonable este cálculo es paralelizable al poder comprobar cada punto por separado pero, debido a que algunos números son descartables muy fácilmente y otro no queda cierta descompensación en tiempo de cálculo.

Aun así esta descompensación no es realmente importante al dividirse el cálculo entre los procesadores disponibles y no tener estos dependencias entre sí.