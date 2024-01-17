Primero para añadir el soporte de la coma flotante se añade el propio banco de registros para coma flotante, sus bloques de cálculo y se usa el mismo circuito de acceso a memoria, permitiendo la conexión tanto desde el banco de registros de enteros como del banco de registros de coma flotante. Además en la entrada del dato a memoria se añade un multiplexor para escoger entre enteros y coma flotante.

Además de todo esto se tienen dos puertos de entrada en el banco de registros para permitir la entrada de datos de memoria y de cálculo a la vez.

## Riesgos estructurales

El caso de la división es el único que genera riesgos estructurales irresolubles por segmentación. Para controlar este riesgo estructural se usa un bit de unidad ocupada. Además genera riesgo estructural al ser un procesador no lineal y poderse solapar la escritura de datos de una división con una suma o una multiplicación, de forma que hay que retrasar la ejecución en este caso también.

### Riesgos de datos

#### Tratamiento

Se guardan todos los registros destino de las instrucciones en ejecución y se comparan en D/L con la actual, parando la ejecución en caso de coincidir alguna. Para llevar a cabo esto se usa un vector de marcas, de forma que en D/L se pone la posición referente al registro con un 1 y cuando se puede leer por cortocircuitos se pone a 0.

### Detección

#### WAW

`VM[Rd] == 1 && Valid(Rd) -> WAW`
#### RAW

Cálculo:
`(VM[Ra] == 1 && Valid[Ra]) || (VM[Rb] == 1 && Valid[Rb]) -> RAW`

Fstore:
`(VM_ent[Rb] == 1 && Valid(Rb)) || (VM_cf[Ra] == 1 && Valid(Ra))`

## Cortocircuitos

Productores: ALU, M2, E4, D20
Consumidores: D/L, M1(ST) (a la última no se le añade por ahrro de costes y simplificación).