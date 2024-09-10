Los mensajes de este protocolo se encapsulan directamente en IP, es decir, sin usar TCP o UDP, es puramente capa 3.

## Contenido de la cabecera OSPF

- Versión
- Tipo
	- Hello
	- Descripción de la LSBD
	- Petición de LS
	- Actualización de LS
	- Confirmación de LS
- Longitud del paquete
- Router ID
- Area ID
- Checksum
- Tipo de autenticación
- Datos de autenticación

## Mensaje Hello

Sirve para descubrir los routers vecinos y crear las adyacencias. También seleccionan el Designated Router y el Backup Designated Router en redes de acceso múltiple y verifican la conectividad con routers vecinos.

### Proceso

1. La interfaz está en estado down
2. Al iniciar OSPF se envía un Hello en broadcast/multicast en la red identificado con su RID y se va haciendo de forma periódica.
3. Al recibir un Hello un router con OSPF activado pasa a estado init y contesta con un Hello con su RID y el recibido.
4. Cuando se recibe un Hello con los dos RID se pasa a estado two-way.

Una vez finalizado este proceso cada router conoce a sus vecinos.

Cuando pasan 4 periodos de Hello sin recibir una respuesta del otro router este se da por caído.

En sistemas con routers conectados entre ellos con varias conexiones (redes con acceso múltiple y broadcast) es necesario elegir un DR y un BDR en base al RID, siendo el DR el que lo tiene más alto y el BDR el siguiente. El resto de routers se designan como OTHER y solo crean adyacencia con DR y BDR y Dr y BDr crean adyacencia entre ellos y con los OTHER.

De esta manera cuando un LSA llega al DR se envía a los BDR y a OTHER; si llega a un OTHER este lo manda a DR y BDR y de ahí DR envía a los otros OTHER y a BDR, recibiendo el segundo el mensaje duplicado; si el LSA llega a BDR este lo manda a DR y este lo envía a los OTHER y BDR, recibiendo este el mismo mensaje dos veces.

Con esto el flooding es mucho más eficiente.

BDR tiene que recibir siempre dos copias para poder comprobar que DR ha hecho su trabajo como se debe. De esta manera cuando BDR recibe un LSA de una red externa o de un OTHER inicia un temporizador y si no recibe antes de que pase el mensaje de DR se toma a este como que le ha pasado algo y BDR toma su trabajo. Se comprueba si DR ha caído con los Hello de verificación que se siguen enviando a todos los vecinos y no solo a adyacencias. En caso de que caiga BDR pasa a ser DR y se selecciona otro BDR.