En una desconposición iterativa la granularidad se define por el número de iteraciones del bucle que ejecuta cada tarea.

```C
void vector_add(int *A, int *B, int *C, int n) {
	int who = omp_get_thread_num();
	int nt = omp_get_num-threads();
	int BS = n / nt;
	for (int i = who*BS; i < (who+1)*BS; i++)
		C[i] = A[i] + B[i];
}
void main() {
	....
	#pragma omp parallel
	vector_add(a, b, c, N);
	...
}
```

Por ejemplo en este caso se divide la ejecución del bucle en `nt` tareas de `BS` iteraciones.

```C
void vector_add(int *A, int *B, int *C, int n) {
	int BS = ...
	for (int ii=0; ii< n; ii+=BS)
	#pragma omp task
		for (int i = ii; i < min(ii+BS, n); i++)
			C[i] = A[i] + B[i];
}
void main() {
	...
	#pragma omp parallel
	#pragma omp single
	vector_add(a, b, c, N);
	...
}
```

```C
void vector_add(int *A, int *B, int *C, int n) {
	int BS = ...
	#pragma omp taskloop grainsize(BS) // or alternatively num_tasks(n/BS)
	for (int i=0; i< n; i++)
		C[i] = A[i] + B[i];
}

void main() {
	#pragma omp parallel
	#pragma omp single
	...
	vector_add(a, b, c, N);
	...
}
```

Estos dos casos dividen en tareas de `BS` iteraciones.