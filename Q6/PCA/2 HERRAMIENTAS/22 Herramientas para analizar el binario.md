`readelf` permite ver los metadatos del binario, por ejemplo la arquitectura. `$ readelf -h program.exe`

`ldd` permite ver las librerías. `$ ldd -h program.exe`

`nm` permite ver los símbolos. `nm program.exe`

`objdump` permite ver el ensamblador del programa. `$ objdump -d program.exe`