# BMS-Bandonberry

## Arduino Pro Micro

[HARDWARE DOCUMENTATION](https://wiki.eprolabs.com/index.php?title=Arduino_Pro_Micro)

Uso de pines:

|uso            |función        |pin     |pin     |función     |uso       |
|---------------|---------------|--------|--------|------------|----------|
|-              |TX/D0          |1       |2       |RAW         |-         | 
|-              |RX/D1          |3       |4       |GND         |-         | 
|-              |GND            |5       |6       |RESET       |-         | 
|-              |GND            |7       |8       |Vcc (5V)    |-         | 
|-              |SDA/D2         |9       |10      |A3          |-         | 
|-              |SCL/D3         |11      |12      |A2          |-         |
|-              |A6/D4          |13      |14      |A1          |-         |
|ShutDownBot_IN |D5             |15      |16      |A0          |-         |
|RaspState_IN   |A7/D6          |17      |18      |D15/SCLK    |-         |
|PowerOnOff_OUT |D7             |19      |20      |D14/MISO    |-         |
|RaspOff_OUT    |A8/D8          |21      |22      |D16/MOSI    |-         |
|-              |A9/D9          |23      |24      |D10/A10     |-         |


ShutDownBot_IN= señal que recibe del botón de encendido/apagado.

RaspState_IN = señal de la raspberry que indica High=No apagar, Low=Se puede apagar.

PowerOnOff_OUT= señal que enciende el transistor, permitiendo alimentar todo el sistema. High=encendido todo el sistema, Low=Se corta la corriente de todo el sistema (A no ser que se apreiete el botón de encendido) 

RaspOff_OUT=señal que indica a la raspberry que comience el proceso de preparación de apagado. (High 0.5 segundos es un reset, por más de 2  sec es comienzo de proceso de apagado, y por más de 8 sec es apagado forzado).


OBS:La señal de Boot_IN se baja pero la luz de la raspberry se termina de apagar 8 sec después, considerar ese delay en el código

FOTO DEL CIRCUITO DEL BOTON



EN RASPBERRY

SHUTDOWN_IN = 12    conectado a        RaspOff_OUT=8

BOOT_OUT = 16       conectado a        RaspState_IN=6         




## Medidor de batería
Utilizaremos un integrado MAX 17043 como medidor de la carga de la batería. [Algo más de info técnica] (https://www.maximintegrated.com/en/products/power/battery-management/MAX17043.html)

Para poder usarlo en Arduino nos bajamos la librerías de aqui:
[Librerias del MAX 17043 Fuel gauge](https://github.com/awelters/LiPoFuelGauge)

Sobre la programación y funciones de la librería
 [Funciones de libreria] (http://www.lucadentella.it/max17043-libreria-per-arduino/)


