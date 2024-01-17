Los procesos para comunicarse tienen que usar un sistema que permite la comunicación entre ellos. Al no tener memoria compartida entre ellos como tal hay que usar otros sistemas como un sistema de ficheros a través de pipes.

Esta comunicación se realiza con llamadas a sistema.

Para evitar este problema y permitir la ejecución paralela de código pudiendo compartir recursos se usan los threads.

De esta manera un proceso puede tener varios threads pero un thread no puede estar en varios procesos a la vez.

## Cambios en definiciones

De esta manera los procesos como tal no se ejecutan, se ejecutan los threads y el planificador se encarga de controlar los threads. Los procesos son únicamente contenedores de información.

## Recursos no compartidos para los threads

- TCB (PCB para los threads)
- User stack
- System stack
- Thread local storage (TCS)
	Es un pedazo de memoria que contiene diferentes datos:
	- errno

## Recursos compartidos entre threads

- Memoria
- Sistema de ficheros
- Programación de signals