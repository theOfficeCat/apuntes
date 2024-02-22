## Access-list

| número | acción | protocolo | @IP origen | puerto origen | @IP destino | puerto destino | estado |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 101 | permit | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 80 |  |
| 101 | permit | TCP | 0.0.0.0/0 | $\ge$ 1024 | N4 | 53 |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
| 101 | deny | any | 0.0.0.0/0 | nu c | 0.0.0.0/0 | nu c |  |

Las listas de acceso se aplican en la interfaz más cercana a lo que se quiere proteger.