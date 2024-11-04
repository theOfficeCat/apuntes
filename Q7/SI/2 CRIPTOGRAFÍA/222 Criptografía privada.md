Origen y destino usan la misma clave secreta, por lo que es una criptografía simétrica. Requiere el intercambio de esta clave a través de un sistema seguro, lo que es un problema.

Se suele basar en un cifrado en bloques, donde X conjunto de bis siempre se traduce por Y conjunto de bits. Aunque también se encuentra encriptación de flujo.

## One Time Pad

Los bloques se cifran usando una clave secreta aleatoria de la misma longitud que el bloque.
## Data Encryption Standard

Utiliza bloques de 64 bytes y una clave de 56 + 8 de paridad.

Funcionamiento:

1. Permitación inicial
2. 16 rondas F
	1. División en 2 semibloques de 32 bits ($S_1$ y $S_2$)
	2. Duplicación de $S_1$
	3. A la copia de $S_1$ se le aplica la función de Feistel con una subclave y se combina con el semibloque $S_2$ a través de una xor.
		1. Expansión: Se expande de 32 a 48 bits duplicando bits.
		2. Mezcla: XOR con una subclave de 48 bits.
		3. Substitución: se dividen los 48 bits en 8 subbloques de 6 bits. Se le aplica una transformación no-lineal que transforma en una salida de 4 bits.
		4. Permutación: reordenación de las salidas en un resultado de 32 bits.
	4. La otra copia de $S_1$ se pasa a la siguiente ronda.
	5. En la siguiente ronda se intercambian $S_1$ y $S_2$ y se vuelve al paso 2.
3. Permitación final (inversa a la inicial)

El descifrado funciona igual pero invirtiendo el orden de aplicación de las subclaves en F.

## 3DES

Aplicar DES 3 veces con una clave total de 168 bits.

No tiene vulnerabilidades conocidas pero es muy lento para grandes cantidades de datos.
## AES

