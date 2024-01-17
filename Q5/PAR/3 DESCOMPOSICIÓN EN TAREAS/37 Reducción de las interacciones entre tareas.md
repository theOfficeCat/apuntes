Se pueden replicar estructuras de datos clave y trabajar localmente con estas hasta que al final se combinan en el resultado final global.

```C
int result = 0;
// Assume this function is instantiated as a task
void dot_product(int *A, int *B, int n) {
	for (int i=0; i< n; i++)
		#pragma omp atomic
		result += A[i] * B[i];
}
```
se puede convertir en
```C
void dot_product(int *A, int *B, int n) {
	int tmp = 0;
	for (int i=0; i< n; i++)
		tmp += A[i] * B[i];
	
	#pragma omp atomic
	result += tmp;
}
```

o especificando las operaciones de reducción explícitamente al generar las tareas con:

```C
#pragma omp parallel
#pragma omp single
{
	#pragma omp taskgroup task reduction(+: sum)
	for (i=0; i< SIZE; i++)
		#pragma omp task firstprivate(i) in reduction(+: sum)
		sum += X[i];
}
```
o
```C
#pragma omp parallel
#pragma omp single
{
	// implicit taskgroup in taskloop construct
	#pragma omp taskloop reduction(+: sum)
	for (i=0; i< SIZE; i++)
		sum += X[i];
}
```

## Sincronización a bajo nivel con locks

Son variables especiales que se sitúan en memoria con dos operaciones básicas:

- Acquire: mientras un hilo está en el bloqueo nadie puede pillarlo, de forma que permite realizar el trabajo en privado sin que otros intervengan
- Release: permite a otros hilos adquirir el bloqueo y hacer su trabajo de forma privada.

```C
omp_lock_t hash_lock[SIZE HASH];
#pragma omp parallel
#pragma omp single
{
	for (i = 0; i < SIZE HASH; i++) omp_init_lock(&hash_lock[i]);
	#pragma omp taskloop
	for (i = 0; i < SIZE_TABLE; i++) {
		int index = hash_function (dataTable[i], SIZE_HASH);
		omp_set_lock(&hash_lock[index]);
		insert_element(dataTable[i], index, HashTable);
		omp_unset_lock(&hash_lock[index]);
	}
	for (i = 0; i < SIZE HASH; i++) omp destroy lock(&hash_lock[i]);
}
```

Esto permite insertar los elementos de forma paralela en diferentes slots pero de forma serie en caso de que sea el mismo.