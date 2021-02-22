#Test Control Remoto IR

Vamos a ejecutar un sencillo programa que nos vaya diciendo los códigos que lee las diferentes teclas utilizando la función key de la [librería NEC.py](/52-libreria-necpy.md)

Fichero [Test-ControlRemoto-IR.py](https://github.com/JavierQuintana/AlphabotPython/)


```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

from VARIABLES import *

import MOVIMIENTOS
import MOVIMIENTOSPASO
import NEC

while True:
    key=NEC.getkey()
    if (key != None):
        print (key)
```
Lo que nos sale por pantalla son los siguiente códigos de las diferentes teclas del mando siguiente:

![](/assets/IRcontrolremote.jpg)

Estos son los valores (ordenados tal y como están en el mando)

|Tecla|Valor|Tecla|Valor|Tecla|Valor|
|-----|-----|-----|-----|-----|-----|
|CH-|69|CH|70|CH+|71|
|<<|68|>>|64|>|67|
|-|7|+|21|EQ|9|
|0|22|100+|25|200+|13|
|1|12|2|24|3|94|
|4|8|5|28|6|90|
|7|66|8|82|9|74|




