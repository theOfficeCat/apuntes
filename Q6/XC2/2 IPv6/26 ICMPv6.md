Es el protocolo de supervisión de IPv6 incluyendo nuevos errores debido a los cambios en la cabecera IPv6.

También incluye el protocolo ARP de IPv4 para conocer si una IP está en uso mandando un mensaje multicast con la IP que se quiere descubrir

## Asignación de routing-prefix global + ULA

- Al arrancar una máquina esta tiene @IPv6 ::/128
- Se envía un ICMPv6 de tipo Router Solicitation en multicast pidiendo configuración global y ULA
- Un router va enviando periódicamente un ICMP de tipo Router Advertisement o como repuesta a RS en multicast con la información solicitada.