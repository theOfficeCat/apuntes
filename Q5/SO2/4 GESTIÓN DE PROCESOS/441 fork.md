Creación de un nuevo proceso copiándose del padre.

```C
int sysfork()
{
	task_union new_task;
	PID = random(); // para evitar que el PID de información del proceso
	new_task = current();
	new_task->PID = PID;
}
```

La tabla de páginas del hijo asigna todas las páginas del padreen diferentes páginas físicas para poder tener la memoria de los procesos independiente entre ellos.

Al no estar las páginas del hijo en la tabla de páginas del padre no se puede acceder a sus páginas físicas a través del TLB. Para resolverlo se hace un mapeo temporal en la tabla de páginas del padre. Al terminar este mapeo se hace un `set_cr3()`

Se inicializan el resto de estructuras del [[42 PCB]].

Se prepara la pila de sistema para que ejecutando un `task_switch()` se pueda ejecutar el proceso sin problemas.

Para devolver un 0 al proceso hijo se usará una función `ret_from_fork()`

```C
int ret_from_fork()
{
	return 0;
}
```

```asm
push %ebp
%ebp <- %esp
%eax = 0
%esp <- %ebp
pop %ebp
ret
```

para ejecutar esta función al ejecutar el proceso por primera vez se sustituye el `%ebp` de la pila de sistema por la dirección de `ret_from_fork()` y se pone un 0 en la cima de la pila.

Por como se ha dejado la pila de sistema tras ejecutar `ret_from_fork()` se regresa al handler de la syscalls y no a la rutina del fork.