## RUN

Se determina que un proceso está en *RUN* cuando no está encolado en ningún lugar.

### Cambio de contexto

Un cambio de contexto implica sacar un proceso del estado *RUN* y meter otro a la vez.

### Funcionamiento

1. Interrupción de reloj de tiempo real
	1. Guardado de contexto en pila de sistema
	2. SAVE_ALL
	3. llamada a la rutina
		1. llamada a schedule
			1. se pilla al primer elemento de la ready_queue
			2. llamada a task_switch(task_union \*new)
				Como todo proceso ha salido de ejecución a través de `task_switch` la pila de sistema de este proceso es igual que la de current.
	4. retorno a modo usuario con el contexto ya cambiado.




```C
void task_switch(task_union *new)
{
	// push %ebp
	// %ebp <- %esp
	current()->kernel_esp = %ebp;
	%esp = new->task_struct.kernel_esp; // current devuelve un task_struct y por eso no es necesario poner el task_struct.

	%tssesp0 = &new->stack[1024];
	set_cr3(new->task.TP);

	// pop %ebp
	// ret
}
```


