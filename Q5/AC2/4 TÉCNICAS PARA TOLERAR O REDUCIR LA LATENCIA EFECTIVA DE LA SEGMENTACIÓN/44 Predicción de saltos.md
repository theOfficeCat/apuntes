Se pueden dejar ejecutados las instrucciones mientras se hace la evaluación del salto, de forma que si se tiene que saltar solo se insertan NOPs en las etapas D/L y BUS pero que en caso de no tener que hacerlo ya se ha acelerado ese trabajo.

La otra posibilidad para los saltos es predecir que se va a saltar, teniendo una penalización inicial de un ciclo por la recepción de la instrucción y el cálculo del salto.

## Decidir si predecir si salta o no

Hay diferentes métodos para decidir que tipo de predicción hacer:

- Salta
- No salta
- Saltar si es hacia atrás y no saltar si es adelante (los fors saltan hacia atrás y se repiten mucho y los ifs si saltan lo hacen adelante, pudiendo optimizar el código poniendo que la condición habitual sea no saltar)