## Hub

Recibe una trama por una interfaz y la transmite por todas las demás interfaces sin modificar la trama, actuando como un repetidor multipuerto.

## Switch

Recibe una trama y la guarda en un buffer, lee la cabecera de la trama y decide la interfaz de salida por la que debe enviarse a partir de la dirección MAC de destino a partir de una tabla llamada Tabla MAC. Esta tabla es dinámica y se va actualizando al comprobar la dirección MAC de las tramas.

No llega a usar la dirección IP

## Router

El router mira la trama y comprueba si la MAC de destino coincide con la de su tarjeta.

- Si coincide
	Elimina la cabecera y guarda el datagrama IP que queda

	



- Si no coincide
	Descarta la trama





