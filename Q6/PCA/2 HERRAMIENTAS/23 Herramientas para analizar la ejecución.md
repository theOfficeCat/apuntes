## Accounting

Por ejemplo el comando `/usr/bin/time`. Da información global de tiempo, uso de memoria, fallos de página, % de CPU (tiempo que ha estado usando CPU respecto al total de ejecución, lo normal es estar en +90% si no hay mucha espera a I/O).

`perf` 
- stat
	- `perf stat -r N [-d[d[d]]]
	N es el número de ejecuciones de las que recopilar información de los eventos de contadores hardware y elapsed. Además calcula la desviación estándar y la media.

    Los -d es el nivel de detalle de estos datos.
- record
- report
- annotate

`oprofile` es lo que había antes de `perf`. Contiene la herramienta `ocount` que recopila esta información de los contadores hardware.

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

---


### Contadores hardware

Los contadores hardware son contadores que se encuentran dentro del procesador que van recopilando información (instrucciones ejecutadas, fallos de página, etc.). Se pueden programar para generar interrupciones cuando se llega a cierto valor.