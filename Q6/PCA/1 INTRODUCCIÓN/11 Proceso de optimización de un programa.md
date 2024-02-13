1. Analizar input y output.
	- El input debe ser representativo.
	- Se genera el golden output, es decir, el output correcto para después comprobar que las optimizaciones sigan siendo correctas.
1. Compilar.
	- Optimizaciones del compilador.
2. Evaluar.
	1. Accounting: Resumen de uso de recursos.
	2. Profiling: Información por líneas o funciones de la ejecución.
	3. Tracing: Extrae, strace.
	4. HLS
	
    Con esta información ya se puede ver qué hay que mejorar del código.
4. Ejecutar la posible mejora y se comprueba la corrección del output comparando con el golden output.
5. Timing: comprobar el tiempo de ejecución.
6. Volver al punto 2.

