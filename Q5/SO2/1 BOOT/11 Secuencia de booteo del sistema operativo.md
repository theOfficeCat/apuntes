
Pasos

1. Alguien pulsa el botón de encendido en el ordenador
2. La placa base hace un chequeo de todos los componentes conectados y que tengan corriente
3. Se levanta una señal de reset para inicializarlo todo
4. La placa busca los componentes para bootear:
	1. CPU
	2. Memoria
	3. Código para bootear: BIOS (Basic I/O System)
			Esta BIOS se encuentra en una EEPROM.
5. La BIOS realiza un reconocimiento de hardware con información relacionada con este. Por ejemplo, procesador: frecuencia base, modelo; memoria: frecuencia, tamaño; disco: marca, espacio.
6. Busca una tarjeta de vídeo (requerida en BIOS actuales) y un dispositivo booteable para ejecutar el sistema operativo que se encuentra en este dispositivo (disco duro, USB, red, etc.). [[111 Booteo del disco duro]]
7. Con el bootloader cargado inicializa el kernel. [[112 Inicialización del kernel]]

