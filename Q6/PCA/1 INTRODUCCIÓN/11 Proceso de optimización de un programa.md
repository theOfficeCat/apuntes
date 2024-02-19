1. Analizar input y output.
	- El input debe ser representativo.
	- Se genera el golden output, es decir, el output correcto para después comprobar que las optimizaciones sigan siendo correctas.
1. Compilar. [[111 Generación del código]]
	- Optimizaciones del compilador.
2. Evaluar. [[112 Análisis de rendimiento]]
	1. Accounting: Resumen de uso de recursos.
	2. Profiling: Información por líneas o funciones de la ejecución.
	3. Tracing: Extrae, strace.
	4. HLS
	
    Con esta información ya se puede ver qué hay que mejorar del código. [[113 Cuando se tiene que optimizar el código]]
4. Ejecutar la posible mejora y se comprueba la corrección del output comparando con el golden output. [[114 Comprobar corrección del programa]]
5. Timing: comprobar el tiempo de ejecución. [[115 Comprobar mejora del rendimiento]]
6. Volver al punto 2.

