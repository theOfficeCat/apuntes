Es una estructura de datos que contiene todos los datos necesarios por el SO para ejecutar el proceso. Con ciertos campos:

- PID
- Tabla de páginas
- Datos sobre el sistema de ficheros
- ...

En Linux se le conoce como 
```C
struct task_struct
```
En Windows se le conoce como `KPROCESS`.

Para encontrar el PCB del proceso actual en ejecución en Windows se tiene el registro `%gs` que apunta constantemente al PCB de este proceso. En Linux se hace de otra forma:

```C
current()
{
	return (%esp)&0xFFFFF000
}
```

Cada proceso tiene la estructura siguiente:

```C
union task_union {
	struct task_struct { // PCB
		int PID;
		*tp;
		list_head;
		kernel_esp;
		...
	}
	unsigned long stack[1024]; // Pila de sistema
}
```

Cuando el compilador encuentra esta `union` primero calcula el tamaño de las diferentes estructuras y le asigna el tamaño del campo más grande a la estructura. Al momento de montar la estructura todas las estructuras se generan con un offset 0, de forma que las diferentes estructuras se solapan en memoria.

Estos `union` se fuerzan a estar alineados con las páginas de memoria.