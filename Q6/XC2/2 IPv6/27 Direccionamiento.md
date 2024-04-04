## Stateful

Conocimiento completo de los estados, una entidad se encarga de evitar la duplicidad de las direcciones como usando DHCP.


## Stateless

No conoce todos los estados y cada host se autoconfigura de forma correcta sin duplicar las direcciones.

### Configuración

1. Host pide routing-prefix y ULA con ICMPv6
2. Genera la parte de interfaceID y completa la dirección
3. Se verifica la dirección como única enviando un DAD (Mensaje ARP para comprobar que no se esté usando la dirección)
4. Si es única se asigna a la interfaz, si no se vuelve al punto 2

#### Generación de interfaceID

##### Usando la MAC

se transforma la MAC en un número de 64 bits metiendo .ff.fe en el centro y cambiando el séptimo bit de la MAC.

##### Generación aleatoria

Pues eso, aleatoria.

---

##### Uso general

MAC para redes internas, aleatoria para redes externas.