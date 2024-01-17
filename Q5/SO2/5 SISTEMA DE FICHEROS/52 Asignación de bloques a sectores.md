## Asignación con bloques iguales, sin compartir sectores

Para utilizar al 100% la capacidad del disco todos los ficheros deben tener un tamaño múltiplo del bloque. ---> existe fragmentación interna.

## Asignación con bloques diferentes, sin compartir sectores

Sigue habiendo fragmentación interna al perder espacio interno del sector aunque los bloques puedan reducirla.

## Bloques diferentes, compartiendo sectores

Ta chido pero muy ineficiente en tiempo de ejecución.

---

Los bloques se puede asignar de diferentes formas:

## Asignación contigua

Los bloques de un mismo fichero se asignan al lado. ---> generan fragmentación externa.

### Asignación estática

Se evita la fragmentación por aumentar un fichero limitando el espacio que puede usar en la creación.

Esto se usa en dispositivos de solo lectura como los CD.

ISO 9660

## Asignación encadenada

Se guardan los últimos bytes de un bloque para apuntar al siguiente bloque.

El acceso aleatorio es una mierda.

## Asignación encadenada en tabla (FAT)

Se tiene una tabla llamada FAT con N posiciones siendo N la cantidad de bloques que guarda el siguiente bloque al que pertenece el referido por la posición de la tabla.

Genera el problema de necesitar un espacio de disco dedicado a la FAT e igual con la memoria.