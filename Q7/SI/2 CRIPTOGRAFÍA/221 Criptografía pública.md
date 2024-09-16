Es una criptografía asimétrica donde cada extremo tiene una clave pública y privada que se generan a través de un algoritmo de generación de claves. Los algoritmos de cifrado y descifrado son público.

## Funcionamiento

### En origen
- El origen A quiere transmitir un mensaje $M$ a B
- A coge la clave pública $PK_b$ de B
- A computa $M' = E_{PK_b}(M)$
- A envía el mensaje $M'$ a B

### En destino
- El destino B coge su clave provada $SK_b$
- B computa $D_{SK_b}(M') = M$
- B puede leer M descifrado