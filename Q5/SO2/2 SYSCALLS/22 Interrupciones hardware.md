Interrupciones provocadas por el hardware. Son las únicas interrupciones que son asíncronas.

La CPU tiene un pin para interrupciones y con un componente llamado PIC multiplexa el dispositivo que la genera.

Tal y como funciona el hardware una vez dentro de una interrupción hardware no van a llegar más mientras esté en modo sistema.

Se lanza el EOI (aviso para permitir más interrupciones) nada más hacer el SAVE_ALL [[24 Funcionamiento del SO]] en interrupciones como el clock o después del `call` como en las interrupciones de teclado.

Dependiendo de la excepción que se lance se puede tener algún parámetro extra después del guardado del contexto hardware.