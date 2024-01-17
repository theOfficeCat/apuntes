Hay 2 flags dentro del registro de la palabra de estado del procesador para el nivel de privilegio. [1121 Niveles de privilegio](1121%20Niveles%20de%20privilegio.md)

Además está el registro $CSEIP$ que apunta a la siguiente instrucción para ejecutar y se tiene también la pila con el registro $ESP$ que apunta a la cima de este stack.

Estas llamadas a sistema se encuentran en la IDT [231 IDT](231%20IDT.md)

En caso de que una excepción genere una excepción también en Windows salta el pantallazo azul y en Linux se entra en modo texto y sale una línea diciendo "kernel panic".

Dependiendo del tamaño del sistema operativo se pueden generar llamadas a sistema específicas para el servicio. Con sistemas operativos más grandes es necesario hacer otras cosas.

Para estos casos donde hay demasiadas llamadas que superan la cantidad disponible por hardware en el caso por ejemplo de MS-DOS es que en el registro *%edx* se enviaba el sevicio del grupo de servicios que se encontraban en esa entrada de la IDT.

En la actualidad tanto en Windows como en Linux se usa una única entrada (0x80 en Linux). Además esto permite tener un único *syscall_handler*.

Con esto para seleccionar la llamada a sistema en específico necesaria se envía por el registro *%eax* y a través de una *SYSCALL TABLE* se accede a la dirección de memoria de la función con la instrucción:

```assembly
call *SYSCALL_TABLE(offset, %eax, 4)
```

## Pasar parámetros

### Método antiguo Linux

Usar registros.

`%edx`, `%ecx`, `%ebx`, `%esi`, `%edi`, `%ebp`

Con el *SAVE_ALL* al guardarse en el orden determinado en [24 Funcionamiento del SO](24%20Funcionamiento%20del%20SO.md) ya se está construyendo automáticamente el frame de activación.
### Método Windows

Usa un buffer guardando los parámetros en la pila y pasando un puntero en el registro `%ebx`

### Método actual

Se pasan los 4 primeros parámetros por registro y el resto por buffer.

## Devolución de parámetros

El kernel devuelve un valor $\ge$ 0 si ha salido todo bien y si no devuelve un $-código\ error$. Y después en nivel de usuario ya hace
```C
if (%eax < 0)
{
	ERRNO = -%eax;
	return -1;
}
```

esto debido a que en modo sistema no se tiene acceso a la variable `ERRNO`.

### Problema con %eax

Al hacer el `RESTORE_ALL` se restaura el valor de servicio en el registro, sobreescribiendo el valor que se devuelve.

La solución que se le puede dar es hardcodear en memoria el valor que se quiere tener en `%eax`. Quedando algo así:

```assembly
.syscall_handler
	SAVE_ALL
	CHECKS
	
	call *SYSCALL_TABLE(offset, %eax, 4)
	movl %eax, -24(%ebp)
	
	RESTORE_ALL
```