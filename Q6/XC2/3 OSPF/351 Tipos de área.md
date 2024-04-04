## Troncal

Es el área 0, área por donde toda la información de encaminamiento se debe distribuir. Todas las demás áreas se deben de conectar a esta.

## Secundaria

Todas las demás áreas. Se pueden configurar de diferente manera:

### Stub

Área que no acepta información externa al sistema. El ABR no deja pasar información externa al sistema de la troncal a la stub, sustituyendo esta información por una ruta por defecto que se distribuye por el área.

## Totalmente stub

No acepta información externa al área misma, de forma que se sustituye toda información externa por una ruta por defecto.

### No tan stub

Puede que sea necesario que proporcione tránsito al conectarse a una zona que no usa OSPF en esta secundaria.

### No tan totalmente stub

Lo mismo pero sin aceptar información externa a la propia área.