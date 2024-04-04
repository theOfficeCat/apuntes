Una vez que se han crado las adyacencias los routers deben de sincronizar entre ellos la información de la topología de la red para tener este conocimiento global del sistema de los routers.

## Funcionamiento

1. Se enví un LSA de descripción por flooding con el conocimiento actual del sistema (resumido).
2. Cada router comprueba este LSA con su conocimiento. Si el número de secuencia es mayor al almacenado envía un LSA de request al router de origen.
3. El router de origen responde con un LSA de update con la información completa.
4. El router que recibe esta información actualiza los datos y envía un LSA de ack para confirmar la recepción.
