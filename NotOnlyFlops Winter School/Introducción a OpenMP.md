Sistema para paralelizar programas con paralelismo a nivel de thread e implícito.

OpenMP es un estándar

Librerías:

- Compilador GNU
	- -fopenmp -> libgomp.so
- Compilador Intel
	- -qopenmp -> libiomp.so

## Modelo fork-join

Un equipo de threads se crea cuando se inicia una región paralela (fork) y cuando esta termina se eliminan excepto el master (join).