Hay diferentes tipos de dispositivos a los que se pueden acceder:

- Dispositivos virtuales
- Dispositivos lógicos
	- Permiten:
		- Abstracción
		- Integración
		- Nuevas características
- Dispositivos hardware

Los dispositivos físicos no son accesibles directamente por el usuario pero tienen un código que accede directamente a este dispositivo (Device Driver).

Los dispositivos lógicos son una abstracción implementada por el SO para representar un dispositivo físico que es visible desde el nivel de usuario.

Los dispositivos virtuales son una interfaz que usa el código de usuario para acceder a un dispositivo, generado el SO a través de una llamada a sistema para asociarlo con un dispositivo lógico.


---

MAJOR: tipo de dispositivo
minor: dónde está conectado (por ejemplo)

---

Cuando un proceso realiza una entrada/salida en un dispositivo este se bloquea para permitir que se mantenga el uso de la CPU mientras se espera la entrada/salida.