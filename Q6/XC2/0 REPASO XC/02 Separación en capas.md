Al ser Internet un sistema complejo y dinámico se decidió "dividir" Internet en diferentes capas para gestionar cada cosa en una u otra. Esta organización está basada en 7 capas.

Esta organización en capas permite que si se genera una nueva tecnología (5G por ejemplo) solo es necesario añadir este protocolo nuevo sin modificar el resto.

## Capas ISO/OSI

1. Físico: cableado y todo eso.

   En este tipo de nivel se estandariza los voltajes, velocidades de
   transmisión, cómo se envían los bits, tipos de conector, pines, etc. En este
   nivel solo se habla de bits o caracteres.

   Ejemplo: estándar RS-232.

2. Enlace: interfaces.

   Hace de interfaz entre el nivel de red y el físico. El PDU que usa se llaman
   frames. Entre sus funciones está:
   - Framing: descubrir donde comienza y acaba un frame dentro del flujo de
     bits o caracteres que leen del nivel físico.
   - Detección de errores.
   - Recuperación de errores: en caso de haber errores puede pedir que se
     vuelva a transmitir el frame.
3. Red: distintas redes
4. Transporte: crea los paquetes, gestiona que todos lleguen en el orden que
   deben y manteniéndose cómo deben ser
5. Sesión: identifica a los usuarios que se conectan al servidor
6. Presentación: las diferentes aplicaciones que funcionan dentro del mismo
  dispositivo y se encarga de representar esta información de los diferentes
  programas
7. Aplicación: cada aplicación que usa la red

```txt
+-----------------+                                     +-----------------+
| 7. Aplicación   | <---------------------------------> | 7. Aplicación   |
+-----------------+                                     +-----------------+
| 6. Presentación | <---------------------------------> | 6. Presentación |
+-----------------+                                     +-----------------+
| 5. Sesión       | <---------------------------------> | 5. Sesión       |
+-----------------+                                     +-----------------+
| 4. Transporte   | <---------------------------------> | 4. Transporte   |
+-----------------+            +-----------+            +-----------------+
| 3. Red          | <--------> | 3. Red    | <--------> | 3. Red          |
+-----------------+            +-----------+            +-----------------+
| 2. Enlace       | <--------> | 2. Enlace | <--------> | 2. Enlace       |
+-----------------+            +-----------+            +-----------------+
| 1. Físico       | <--------> | 1. Físico | <--------> | 1. Físico       |
+-----------------+            +-----------+            +-----------------+
        |________________________|       |________________________|
    Nodo terminal               Nodo intermedio               Nodo terminal
```
## Capas TCP/IP

7-5 -> Aplicación de red

4 -> Transporte

3 -> Enlace

2-1 -> Interfaz de red

---

## Transmisión de datos

La transmisión de datos se realiza a partir de tramas que recorren las 7 capas hasta el nivel físico para llegar al destino y volver a "subir".
