Al ejecutarse una instrucción de salto se tiene que parar la ejecución de instrucciones porque no se sabe si se va a continuar linealmente o se va a tener que saltar a un CP diferente.

En cuanto se decodifica una instrucción de salto se tienen que descartar las 2 instrucciones que han empezado y suspender la interpretación de nuevas transformándolo todo a instrucciones NOP.