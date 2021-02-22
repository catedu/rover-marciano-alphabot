#CONTROL REMOTO

¿Qué esperas? te lo pide el cuerpo !!! vamos a hacer un control remoto del robot !!

Vamos a definir las siguientes teclas

gobernado por el teclado *numérico*:

* PARAR = tecla 5
* ADELANTE=FORDWARD = 8
* ATRAS=BACKWARD = 2
* DERECHA=RIGHT = 6
* IZQUIERDA=LEFT = 4

{% youtube %}https://www.youtube.com/watch?v=PfoVh2BTlLY&feature=youtu.be{% endyoutube %}

####Solución
La solución es fácil con las librerías que hemos aprendido:
* Ponemos las librerías fichero [MOVIMIENTOS.py](/24-libreria-movimientospy.md) y ahora esta nueva [NEC.py](/5-control-remoto/51-como-funciona.md) en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* También incorporamos las variables definidas en **VARIABLES.py**
* Utilizaremos los códigos que hemos optenido en [Test Control Remoto IR.](/53-m1-test-control-remoto-ir.md)
* Un bucle, si no detecta la tecla 5 que haga los movimientos según las teclas del mando IR.

%accordion%Solución%accordion%

Fichero [Control-Remoto-IR.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true

import RPi.GPIO as GPIO
import time

from VARIABLES import *

import MOVIMIENTOS
import NEC

vel=50

print ('TECLAS :\nPARAR = tecla 5\nADELANTE=FORDWARD = 2\nATRAS=BACKWARD = 8\nDERECHA=RIGHT = 6\nIZQUIERDA=LEFT = 4')

key=0
while key!=28:
    key=NEC.getkey()
    if (key != None):
        if key==24:
            print ('\nadelante')
            MOVIMIENTOS.FORDWARD(vel)
        if key==82:
            print ('\natrás')
            MOVIMIENTOS.BACKWARD(vel)
        if key==90:
            print ('\nderecha')
            MOVIMIENTOS.RIGHT(vel)
        if key==8:
            print ('\nizquierda')
            MOVIMIENTOS.LEFT(vel)
        if key==28:
            print ('\nFin, has apretado STOP')
            MOVIMIENTOS.STOP()    

```
%/accordion%