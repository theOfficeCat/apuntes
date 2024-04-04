Es un protocolo no propietario.

Al haber un cambio en la información que contiene el router manda un mensaje al resto. Se pueden definir métricar arbitrarias, áreas diferentes y aplicar un encaminamiento jerárquico.

Cara router tiene un conocimiento global y único del sistema, es decir, que conoce la totalidad de la estructura de la red y puede escoger la mejor ruta de envío del mensaje.

## Conceptos básicos

Cada router debe tener un RID único en el sistema.

Se puede configurar de diferentes maneras:

- Manualmente
- @IP más alta entre las @IP asignadas a las interfaces virtuales
- En caso de no crearse interfaces virtuales es la @IP más alta entre las @IP asignadas a interfaces activas del router.

Cada router envía la información al resto de routers cuando se produce un cambio se forma que siempre todos los routers tienen el conocimiento completo de la red para escoger la ruta de envío.

## Funcionamiento

SI le llega un mensaje con la información d eun cambio modifica el conocimiento del sistema y ejecuta un algoritmo de SFP (dijkstra) para poder calcular en base al coste la mejor ruta para la transmisión de los datos.

$coste=\frac{10^8}{ancho\ de\ banda}$

Este valor de referencia se puede modificar por otro arbitrario por ejemplo si se tiene anchos de banda mayores a 100Mbps ya que a partir de ahí todos los costen dan 1 con esta fórmula.

