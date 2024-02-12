1. Analizar input y output.
	- El input debe ser representativo.
	- Hay que ver si es preferible el golden output (mejor output, puede tener diferencias en coma flotante) o el golden code (código más eficiente pero que puede generar desviaciones en el resultado).
2. Compilar.
	- Optimizaciones del compilador.
3. Evaluar.
	1. Acounting: Resumen de uso de recursos.
	2. Profiling: Información por líneas o funciones de la ejecución.
	3. Tracing: Extrae, strace.
	4. HLS
	
    Con esta información ya se puede ver qué hay que mejorar del código.
4. Ejecutar la posible mejora y se comprueba la corrección del output comparando con el golden output.
5. Timing: comprobar el tiempo de ejecución.
6. Volver al punto 2.

