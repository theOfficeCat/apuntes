## Estrategia de la hoja

Cada hoja dentro de la recursión es una tarea nueva.

```C
#define N 1024
#define MIN_SIZE 64
int result = 0;

void dot_product(int *A, int *B, int n) {
	for (int i=0; i< n; i++)
		#pragma omp atomic
		result += A[i] * B[i];
}

void rec_dot_product(int *A, int *B, int n) {
	if (n>MIN_SIZE) {
		int n2 = n / 2;
		rec_dot_product(A, B, n2);
		rec_dot_product(A+n2, B+n2, n-n2);
	}
	else
		#pragma omp task
		dot_product(A, B, n);
}

void main() {
	#pragma omp parallel
	#pragma omp single
	{
		rec_dot_product(a, b, N);
		#pragma omp taskwait
	}	
}
```

que genera un overhead importante al poderse solo ejecutar una actualización de result a la vez, pudiéndose corregir a través de la siguiente modificación

```C
void dot_product(int *A, int *B, int n) {
	int tmp = 0;
	for (int i=0; i< n; i++)
		tmp += A[i] * B[i];

	#pragma omp atomic
	result += tmp;
}
```

El taskwait que se encuentra dentro de main esperará a que terminen de ejecutarse todas las tareas generadas.

Para evitar un exceso de tareas que genere un overhead que no rente se puede utilizar la estrategia de la hoja con un control de profundidad.

## Estrategia del árbol

Cada iteración recursiva genera una tarea.

```C
int dot product(int *A, int *B, int n) {
	int tmp = 0;
	for (int i=0; i< n; i++)
		tmp += A[i] * B[i];
	return(tmp);
}
int rec dot product(int *A, int *B, int n) {
	int tmp1, tmp2 = 0;
	if (n>MIN_SIZE) {
		int n2 = n / 2;
		#pragma omp task shared(tmp1) // firstprivate(A, B, n, n2) by default
		tmp1 = rec dot product(A, B, n2);
		#pragma omp task shared(tmp2) // firstprivate(A, B, n, n2) by default
		tmp2 = rec dot product(A+n2, B+n2, n-n2);
		#pragma omp taskwait
	} else
		tmp1 = dot product(A, B, n);
	return(tmp1+tmp2);
}
void main() {
	#pragma omp parallel
	#pragma omp single
	result = rec dot product(a, b, N);
}
```

Al igual que con la estrategia de la hoja se puede aplicar un control de la profundidad.

Este control de la profundidad se puede hacer usando el operador de OpenMP `final`

```C
#define MIN_SIZE 64
#define CUTOFF 3
...
int rec_dot_product(int *A, int *B, int n, int depth) {
	int tmp1, tmp2 = 0;
	if (n>MIN_SIZE) {
		int n2 = n / 2;
		if (!omp_in_final()) {
			#pragma omp task shared(tmp1) final(depth >= CUTOFF)
			tmp1 = rec_dot_product(A, B, n2, depth+1);
			#pragma omp task shared(tmp2) final(depth >= CUTOFF)
			tmp2 = rec_dot_product(A+n2, B+n2, n-n2, depth+1);
			#pragma omp taskwait
		} else {
			tmp1 = rec_dot_product(A, B, n2, depth+1);
			tmp2 = rec_dot_product(A+n2, B+n2, n-n2, depth+1);
		}
	}
	else
		tmp1 = dot_product(A, B, n);
	return(tmp1+tmp2);
}
...
```