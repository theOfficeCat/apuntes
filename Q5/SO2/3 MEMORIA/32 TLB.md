Sirve para asociar las direcciones lógicas con las direcciones físicas a través de asociaciones de rangos de direcciones del mismo tamaño. Cada uno de estos rangos en la memoria lógica se va a llamar página, página lógica y en la memoria física se van a llamar frame, página física.

Se "evoluciona" la MMU guardando parejas de identificador de página lógica e identificador de frame, además de dos bits de escritura/lectura y un bit de nivel de privilegio.

## Accesos a memoria

En la dirección lógica los 12 bits de menor peso son el offset para trabajar dentro de la página. Los 20 bits de mayor peso restantes son el identificador de página lógica.

Para traducir la dirección física se pasa directamente el offset y a través de la TLB se traduce el identificador de página lógica al identificador del frame.

> Esta traducción se hace pasando el identificador de página lógica a la TLB y consultando de forma paralela todos los identificadores de página lógica para encontrar el identificador del frame.

En caso de fallo de TLB se accede al PCB que contiene la tabla de páginas del proceso. Cada entrada de esta tabla de páginas contiene el identificador del frame, un bit de presencia, dos bits de escritura/lectura y un bit de supervisor.

El procesador tiene un registro `%cr3` que apunta al inicio de la tabla de páginas como dirección .

Por tanto, al momento de acceder al dato al haber fallo primero se comprueba el bit de presencia. En caso de que sea 0 salta un page fault. En caso de ser 1 al ser una dirección válida se coge el id del frame y se coloca en una posición de la TLB y, en caso de no quedar huecos, con un algoritmo pseudo-LRU se sustituye una entrada.

Para las traducciones en modo sistema todos los procesos tienen mapeados el kernel. Para evitar los accesos desde modo usuario al kernel se utiliza el nivel de privilegios de la tabla de página expresado con el bit de supervisor.

## Distribución de la memoria

Se suelen dejar huecos vacíos por cuestiones de seguridad, además de que los diferentes bloques de código, datos y pila puede modificar su tamaño con librerías de enlace dinámico para el código, malloc para los datos o con el crecimiento normal de la pila por el SO.
