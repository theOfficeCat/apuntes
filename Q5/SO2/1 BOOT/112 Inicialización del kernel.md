
1. Inicialización de las estructuras software propias del kernel.
2. Inicialización de las estructuras hardware propias del kernel.
3. Reconocimiento de hardware para obtener toda la información posible para cargar los drivers de los dispositivos.
4. Se crea el proceso *INIT* como proceso de usuario.
5. Se salta a modo protegido, dando el SO el nivel de máximo privilegio. [[1121 Niveles de privilegio]]
	1. Se crean los modos de protección y se activa la paginación de la memoria.
6. Se ejecuta un proceso llamado *TRAMPOLINE* que ejecuta el proceso *INIT* con privilegios de usuario

Además durante la inicialización del kernel se inicializa el IDT [[231 IDT]], asignando al registro *IDTr* la posición de memoria de la IDT.