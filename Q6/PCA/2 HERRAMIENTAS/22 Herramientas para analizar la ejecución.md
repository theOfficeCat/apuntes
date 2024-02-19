## Accounting

Por ejemplo el comando `/usr/bin/time`. Da información global de tiempo, uso de memoria, fallos de página, 

## Profiling

Por ejemplo `gprof` o `valgrind`.

Da información a nivel de función o incluso de línea de código, incluye información de uso de CPU a nivel de usuario.

`valgrind` no necesita el uso de `-pg` pero sí que le vendría bien tener `-g` para poder ver la información referente a líneas de código.

### Como hacer profiling con `gprof`

1. Compilar con `-pg` `$ gcc -pg -g -o program.exe program.c`
2. Ejecutar el programa `$ ./program.exe`
	En base al funcionamiento irá mandando signals al programa y va guardando la información en un fichero en específico (gmon.out).
3. `$ gprog -bp ./program.exe`

## Tracing