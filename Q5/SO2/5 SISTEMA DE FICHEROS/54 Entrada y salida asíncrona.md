Se hace primero la petición de datos y solo se bloquea en caso de requerirlos y no tenerlos disponibles ya.

código usuario:
```C
read_async();
// cosas
isReady();
```

```C
sys_read_async() {

}
```

```C
read_async_dep()
{
	encolar_peticion();
	sem_post(&sem_gestor);
}
```

```C
sys_isReady();
```

```C
isReady_dep()
{
	sem_wait(&sem_op);
	coger_res();
}
```

La versión síncrona se implementa haciendo las dos llamadas seguidas:

```C
sys_read()
{
	sys_read_async();
	sys_isReady();
}
```
