La dependencia de datos indican el orden de ejecución de las instrucciones, pudiendo reordenar las instrucciones para impedir en todo lo posible las dependencias de datos. Por ejemplo:

```
Orden original:
A -> B -> C -> D -> E

Dependencias:
A -> B
C -> D
E

Reordenación:
A -> C -> E -> B -> D
```

Este reordenamiento tiene un límite conocido como bloque básico, siendo este un grupo de instrucciones atómicos, es decir que si se ejecuta la primera instrucción se ejecuta el resto de instrucciones.