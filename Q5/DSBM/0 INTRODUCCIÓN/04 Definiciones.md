
> Bits de configuración: bits en registros del micro que sirve para configurar todo el micro.

## Power-on reset

Hay un tiempo de espera al dar alimentación al chip para asegurarse de que sea estable.

## Brown-out reset

Reset que se envía en momentos donde la alimentación es incorrecta, por ejemplo una caída de voltaje por debajo de un mínimo.

## Watchdog timer

Chip conectado a la CPU que lanza un reset después de un tiempo en específico. Este chip tiene un pin que está conectado desde la CPU que va reseteando el timer antes de que envíe el reset al chip.

Sirve para evitar que se bloquee en un posible bucle infinito el chip en sistemas que no tienen interfaz.

