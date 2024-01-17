## Memoria compartida centralizada

Se tiene una memoria principal compartida al igual que el uso de I/O. Este tipo de arquitectura también se la conoce como UMA (uniform Memory Access (Time)) ya que esta memoria compartida está a la misma distancia aproximada de todos los cores y es igualmente mala de acceder desde todas. También se la llama SMP (Symmetric MultiProcessor) porque todo el conjunto core-cache es idéntico y se puede replicar para aumentar el procesador global.

### Problema de coherencia de cache

Está el problema de que cada core tiene su propia cache y puede ser que en una escritura desde un core en otro no se tenga el dato actualizado y se lea un dato antiguo.

#### Solución para el problema

- En cada escritura enviar este dato a todas las caches para que actualicen el valor almacenado. (write-update)
- Las escrituras previenen que otras copias generen hit. (write-invalidate)


- Las escrituras se emiten por un bus compartido y el dato más reciente es el que se usa. (snooping)
-  A cada bloque se le asigna un punto de ordenamiento. (directory)

##### Write-update snooping

Las caches están conectadas entre ellas por un bus que está conectado a la memoria.

###### Lectura

Se emite por el bus la petición de lectura y la memoria devuelve el dato.

###### Escritura

se envía el dato a la memoria principal a través del bus y al estar las otras caches leyendo el bus buscando escrituras actualizarán el dato en las caches también.

En caso de intentarse ejecutar dos escrituras a la vez se ejecutará primero una y después la otra a través de un tipo de mediación al tener un único bus de comunicación entre cores.

##### Write invalidate snooping

La cache contiene un bit de validez, un bit de shared y un bit de dirty.

###### Lectura

Al realizarse una lectura que no está en la cache se pone el bit de validez a 1 y los otros dos a 0.

###### Escritura

Al hacerse una escritura se pone el bit de validez a 0 en las caches donde está guardado el dato y se pone en la cache de escritura la validez a 1, dirty a 1 y shared a 0.

Al realizarse otra lectura responde la cache donde se ha escrito en ambas caches se pone shared a 1.

---

La coherencia Snooping tiene un problema de cuello de botella al tener un único bus limitado a una transmisión simultánea.

#### Directorio

Es una estructura distribuida a través de los cores donde cada pedazo del directorio al lado del core contiene un conjunto de bloques.

Cada pedazo tiene una entrada por cada bloque que contiene y cada entrada de un bloque controla qué caches tienen este bloque en un estado válido. El orden de accesos viene determinado por el pedazo de origen del bloque.

En este protocolo las caches contienen los mismos estados pero el dato en una lectura o escritura no va a través de un bus sino que se pasa por el directorio.

Cada bloque contiene un bit de dirty y los bits de presencia en las caches. Inicialmente todo está inicializado a 0.

###### Lectura

Al realizar una lectura se produce una petición de lectura. Esta se transfiere hasta el pedazo del directorio que contiene el dato. En los datos del directorio, en caso de que no esté el dato en ningún bloque se lee de memoria y se devuelve, marcando el bit de presencia en esta cache y el bit de dirty que se usa para comprobar si una cache necesita reescribirse.

###### Write

se envia la petición de escritura al directorio y si el bloque está presente se envía la petición a las caches donde está presente y se invalida/cambia el dato.