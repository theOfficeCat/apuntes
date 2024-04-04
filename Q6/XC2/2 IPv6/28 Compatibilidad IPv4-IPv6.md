## Dual stack

Un host funciona con dual stack (los dos protocolos) y se adapta según la red y el destino.

## IPv4 mapped

la IPv4 se mapea en los últimos 32 bits de ::ffff:0:0:/96

## Tunneling

Cuando dos aplicaciones usan IPv6 pero en el cmaino hay IPv4 se crea un túnel

- 6to4 2002::/16
- Teredo tunnel si hay NAT IPv4
- Tunnel bróker que se configura a través de un server

## NAT64

Cuando una aplicación IPv6 comunica con IPv4 se usa el rango reservado 64:ff9b::/96 poniendo la IPv4 al final