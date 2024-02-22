Ejemplo Diapos

R2

| adq | Destino/máscara | Gw | interfaz | Métrica |
| ---- | ---- | ---- | ---- | ---- |
| C | 10.0.1.0/24 | - | e1 | 1 |
| C | 10.0.4.0/24 | - | e0 | 1 |
| C | 10.0.2.0/24 | - | fe0.1 | 1 |
| C | 10.0.3.0/25 | - | fe0.2 | 1 |
| C | 10.0.3.128/25 | - | fe0.3 | 1 |
| R | 10.0.0.0/24 | R1 | e1 | 2 |
| R | N4 | R3 | e0 | 2 |
| R | N1 | R4 | e0 | 3 |
| R | N2 | R4 | e0 | 3 |
| R | N3 | R4 | e0 | 3 |

## Mensajes RIP

Son vectores (contienen diferentos elementos) con cada elemento conteniendo 3 informaciones:

1. Red
2. Máscara
3. Métrica



