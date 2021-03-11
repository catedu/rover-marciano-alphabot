
# CONTROL REMOTO

Vamos a simular la comunicación entre Tierra y el rover.

## ¿Cómo son las comunicaciones entre un rover y la Tierra?

Los rovers envían la señal a alguno de los  satélites artificiales que giran alrededor del sitio donde están, por ejemplo en Marte hay 5 satélites, y estos satélites envían la señal a la Tierra.

![](/assets/comunicacion1.jpg)

Iconos de [Flaticon](https://www.flaticon.es/)

Hay rovers que además de usar la comunicación anterior, tienen dos antenas, una que apunta a la Tierra y otra que apunta a todas las direcciones. Las dos envían la información diréctamente a la Tierra en una banda 7-8 GHz de la "Red del Espacio profundo" que lo forman 3 antenas que están repartidas en la Tierra para que siempre sean visibles desde el rover.

![](/assets/comunicacion2.jpg)

Iconos de [Flaticon](https://www.flaticon.es/)

Una antena está en California, otra está en Camberra y otra ¡¡Está en Madrid!! concretamente en Robledo de Chavela de 70m de diámetro, yo tuve la suerte de visitarla cuando era estudiante !

![](/assets/robledo.jpg)

[De Malopez 21 - Trabajo propio, CC BY-SA 4.0](https://commons.wikimedia.org/w/index.php?curid=52005724)



# VAMOS A ELLO
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
