Sirven para conectar dispositivos dentro del sistema.

## I2C, SPI

Master-slave

I2C (Inter-Integrated Circuit). Está pensado para usarse dentro de la PCB en circuitos cortos. usa 2 cables: SCL (clock) y SDA (data).

## Línea serie

Hay un cable con un estado por defecto y al generarse un primer cambio de bit se marca el inicio de la señal, mandándose después los datos con la posibilidad de un bit de paridad y al final un bit de stop.

El dispositivo que controla un protocolo de línea serie es el UART.

## CAN

Hay un dispositivo como nodo 