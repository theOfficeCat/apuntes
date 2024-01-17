El procesador se genera a sí mismo una excepción cuando pasan cosas que no deben pasar en ejecución de la CPU:

- divisón entre 0
- Acceso de memoria incorrecto
- Ejecución de instrucciones de un nivel de privilegio superior al que se tiene

Las excepciones que dan un código de error al finalizar esta ejecutan un %esp += 4 para eliminar de memoria este registro.