la segmentación provoca posibles lecturas de registros que se tiene que escribir anteriormente pero no se ha hecho todavía.

## En registros

Hay 3 tipos de dependencias de datos:

- Read-after-write (dependencia verdadera) --->
- Write-after-read (antidependencia) -|->
- Write-after-write (dependencia de salida) -o->

Las dos últimas con el procesador actual no son problemáticas pero con procesadores fuera de orden ya pueden dar problemas.

## En memoria

En memoria como no se sabe en un principio las direcciones de memoria, en caso de no poder asegurar que no sean iguales se asumirá que lo pueden ser, de forma que al tener instrucciones de memoria con mismo registro y diferente inmediato se asegura que las direcciones sean diferentes pero con instrucciones con diferentes registros no puede asegurar la diferencia de las direcciones.
