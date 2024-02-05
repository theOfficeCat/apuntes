MPI: Message Passing Interface

A diferencia de OpenMP que es de memoria compartida sirve para memoria distribuida. OpenMP funciona a nivel de threads, MPI a nivel de proceso.

No se usan pragmas sino que se usan directamente llamadas a la librería `MPI_...`.

El communicator es el conjunto de ranks (procesos).

Para compilar usamos el comando `$ mpicc` para evitar escribir el path de include y librería de MPI.

## Comunicaciones

### Point-to-point

Comunicación entre dos procesos en específico.

Funciona con `MPI_Send` desde uno y `MPI_Recv` desde el otro

Estas llamadas pueden ser bloqueantes o no bloqueantes.

#### Bloqueantes

`MPI_Send`, `MPI_Recv`

#### No bloqueantes

`MPI_ISend`, `MPI_IRecv` + `MPI_Wait`, `MPI_Waitall`, `MPI_Waitany`

### Colectivas

Comunicación entre todos los procesos en un communicator.

Un caso bastante común es `MPI_Allreduce(...)` donde se operan una serie de datos y se obtiene un resultado. Esta llamada devuelve el mismo resultado a todos los procesos.