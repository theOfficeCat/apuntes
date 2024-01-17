Realmente las funciones como *read()* o *fork()* no son llamadas a sistema directamente sino wrappers (lib.so en Linux o kernel32.dll en WIndows). Estos wrappers no son más que funciones que ofrecen al programador portabilidad y que ejecuta las llamadas a sistema dentro de estas funciones.

El wrapper al ser una librería se ejecuta también como proceso de mínimos privilegios.

Una vez dentro de modo de sistema se pasa primero al control del contexto de usuario, esto programado en ensamblador.

1. SAVE_ALL: guarda en la pila toda la información necesaria para el SO para volver al modo usuario.
	- GS
	- FS
	- ES
	- DS
	- EAX
	- EBP
	- EDI
	- ESI
	- EBX
	- ECX
	- EDX
2. CHECKS: se hacen comprobaciones necesarias.
3. llamada al código de alto nivel.

El código de alto nivel de la llamada a sistema suele tener como nombre *sys_(nombre)*.

1. Realiza comprobaciones de parámetros.
2. Comprobaciones de sources.
3.  Ejecuta la llamada a sistema en cuestión.