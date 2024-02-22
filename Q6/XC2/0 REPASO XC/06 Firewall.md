## Access-list

### Entrada

| número | protocolo | @IP origen | puerto origen | @IP destino | puerto destino | estado |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 101 | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 80 | new |
| 101 | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 53 | new |
|  |  |  |  |  |  |  |
| 101 | any | 0.0.0.0/0 | nu c | 0.0.0.0/0 | nu c |  |

Las listas de acceso se aplican en la interfaz más cercana a lo que se quiere proteger.

Se puede girar la de salida solo permitiendo en entrada si es una conexión ya establecida, es decir que son respuestas:




| número | protocolo | @IP origen | puerto origen | @IP destino | puerto destino | estado |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 101 | TCP | 0.0.0.0/0 | $\lt$ 1024 | 10.0.0.0/8 | $\ge$ 1024 | established |
|
| 101 | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 80 |  |
| 101 | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 53 |  |
|  |  |  |  |  |  |  |
| 101 | any | 0.0.0.0/0 | nu c | 0.0.0.0/0 | nu c |  |

### Salida


| número | protocolo | @IP origen | puerto origen | @IP destino | puerto destino | estado |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 102 | TCP | 10.0.0.0/8 | $ge$ 1024 | 0.0.0.0/0 | $\lt$ 1024 |  |
|  |  |  |  |  |  |  |
| 101 | any | 0.0.0.0/0 | nu c | 0.0.0.0/0 | nu c |  |
