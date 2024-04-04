Para mejorar la escalabilidad de un sistema OSPF se puede dividir en varias areas, de forma que se tiene bases de datos más pequeñas, con tablas de encaminamiento más pequeñas, un número menor de LSAs y menos recálculos de rutas. Aun así esto genera la necesidad de planificar el sistema para dividirlo en áreas, requiere más configuración y genera puntos críticos de posible desconexión y aislamiento del sistema.

## Tipos de routers

- Internal Router
	- Tiene todas sus interfaces en una misma área y, por tanto, todos los IR de una misma área tienen la misma base de datos.
- Area Border Router
	- Tienen interfaces en diferentes áreas, teniendo una base de datos por cada área.
	- Pueden sumarizar los LSA entre un área secundaria y la troncal.
	- Tienen que reenviar los LSA recibidos al área troncal.
- AS Boundary Router
	- Es un router que tiene al menos una interfaz conectada a OSPF y otra que no. Por tanto, importa informaciónde otros protocolos  para convertirlos a OSPF y transmitir esa información y viceversa.