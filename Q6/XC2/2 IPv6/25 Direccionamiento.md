## Link-local

Sirve para transmitir a destinos de una misma red de origen. Usan como origen y destino el rango fe80::/10

## Site-local

Sirve para transmitir entre un origen y destino dentro de un mismo "sitio", es decir, no enrutables en Internet. Usa el rango fec0::/10

Ha sido deprecado por ser ambigua al no poderse definir como tal qué es un site y porque complejiza la administación de una red con poca intervención en cambios de infraestructura, por ejemplo: dos empresas que se fusionan y unifican sus redes.

### Unique Local Address

Se crea como sustitución de Site-local con la intención de usarse como dirección privada y única. Hay dos formatos que se fundamentan en lo mismo: prefijo de 8 bits, 40 bits para hacer única la dirección y 16 bits para subnetting.

- fc00::/8
	- los 40 bits los proporcionan una entidad centralizada que todavía no está disponible
- fd00::/8
	- Los 40 bits se definen en base a un algoritmo