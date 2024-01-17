
Un procesador x86 ofrece 4 niveles de privilegio (eran 4 al diseñarse los niveles de privilegio de x86 porque se creía que se iban a usar todos):

- 00: permite acceder a todo.
- 01: se usa para ejecutar el kernel en una máquina virtual.
- 10: normalmente no se usa.
- 11: se pueden ejecutar operaciones aritméticas, de control de flujo y acceso a la memoria asignada como proceso.

De esta manera los procesos se ejecutan en el nivel de privilegio 3 para evitar accesos no autorizados a dispositivos, a memoria, etc. En cambio el SO se ejecuta sobre un nivel de privilegio 0.

La palabra de estado de programa contiene 2 bits para almacenar el estado de privilegio en el momento, que se usa para comparar el nivel de privilegio actual con el privilegio requerido por una instrucción para ejecutarse. En caso de no tener un privilegio igual o superior al requerido se lanza una excepción.
