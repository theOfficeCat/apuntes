## Tipo 1

LSA que circula por la misma área

Se representa en la tabla de encaminamiento con una O en la columna de adquisición.

## Tipo 3

Aparece en la tabla de encaminamiento con una O IA en la columna de adquisición.

De una secundaria a la troncal siempre se envía.

De una troncar a secundaria se envía en base al tipo de área:

- Stub: se reenvía por el área
- Totalmente stub: se envía una ruta por defecto en el área

## Tipo 5

Es la que viene de zonas que no usan OSPF

Aparecen de dos formas diferentes en las tablas de encaminamiento:

- O E2: el coste viene definido por el ASBR sin coste de la red interna.
- O E1: el coste lo decide el ASBR y añade un conste OSPF de cada link.

Independientemente del tipo del área secundaria se reenvía una ruta por defecto.

## Tipo 7

LSA que cruza un área secundario NSSA de ASBR a ABR.

Aparece en las tablas de encaminamiento como dos formas:

- O N2
- O N1

los dos en base al mismo criterio que el tipo 5. El ABR traduce el tipo 7 en tipo 5 al entrar en la troncal.