La cabecera IPv6 se simplifica mucho respecto a IPv4 dejando úncamente los siguientes parámetros:

- Versión (4 bits)
- Clase de tráfico (8 bits)
	- Prioridad de paquetes y aviso de congestión
- Etiqueta de flujo (20 bits)
	- Para facilitar la identificación de paquetes de un mismo flujo (secuencia de paquetes relacionados entre sí o  de una misma sesión TCP)
- Logitud (16 bits)
	- La longitud mínima de un datagrama IPv6 es de 1280 bytes.
- Próximo header (8 bits)
	- Especifica el tipo del siguiente header donde se incluyen las opciones que ya no se cuentan en la cabecera IP
- Límite de saltos (8 bits)
	- (TTL)
- Dirección origen (128 bits)
- Dirección destino (128 bits)

