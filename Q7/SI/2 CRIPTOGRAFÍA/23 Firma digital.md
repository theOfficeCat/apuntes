Se usa para autenticar que el mensaje lo envía quién dice ser a través de un sistema que hace que

$S = M + A_{SK}(M)$

siendo $S$ la firma, $M$ el mensaje, $A$ el algoritmo de cifrado y $SK$ la clave privada.

De esta forma debería cumplirse

$D_{SK}(M - S) = M$

siendo $D$ el algoritmo de descifrado.