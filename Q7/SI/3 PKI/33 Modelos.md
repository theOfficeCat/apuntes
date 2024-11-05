## Distribuido

Es el modelo más simple, donde un usuario crea y firma certificados para otros y estos tienen confianza entre ellos. No requiere de tener una TTP (CA).

## Plano

En el modelo simple solo hay una CA que se ha autofirmado el certificado y firma los certificados del resto.

## Jerárquico

Es como el plano pero con diferentes niveles de CA. Para validar el certificado se va subiendo en el árbol hasta llegar a la CA raíz con certificado autofirmado.

## Híbrido

### Confianza jerárquica

Cada aplicación tiene un conjunto de CAs de confianza que acreditan los certificados.

### Cruzada jerárquica

Las CA raiz se emiten certificados entre ellas.