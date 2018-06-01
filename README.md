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
|Boot_IN        |A7/D6          |17      |18      |D15/SCLK    |-         |
|OnOff_OUT      |D7             |19      |20      |D14/MISO    |-         |
|RaspOff_OUT    |A8/D8          |21      |22      |D16/MOSI    |-         |
|-              |A9/D9          |23      |24      |D10/A10     |-         |


ShutDownBot_IN= señal que recibe del botón de encendido/apagado.
Boot_IN= señal de la raspberry que indica High=No apagar, Low=Se puede apagar.
OnOff_OUT= señal que enciende el transistor, permitiendo alimentar todo el sistema. High=encendido todo el sistema, Low=Se corta la corriente de todo el sistema (A no ser que se apreiete el botón de encendido) 
RaspOff_OUT=señal que indica a la raspberry que comience el proceso de preparación de apagado. (High 0.5 segundos es un reset, por más de 2  sec es comienzo de proceso de apagado, y por más de 8 sec es apagado forzado).

OBS:La señal de Boot_IN se baja pero la luz de la raspberry se termina de apagar 8 sec después, considerar ese delay en el código

FOTO DEL CIRCUITO DEL BOTON


