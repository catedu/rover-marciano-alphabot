# PROYECTO FINAL

Para finalizar, vamos a JUNTAR las piezas y hacer nuestro rover un verdadero explorador espacial !! bueno, al menos en lo principal:

![](/assets/ROVER-ALPHABOT.png)

*[Fotomontaje nasa.gov Credits NASA](https://www.nasa.gov/press-release/la-nasa-ofrecer-una-retransmisi-n-en-espa-ol-para-el-aterrizaje-del-rover-mars)*

Con tu creatividad y con las diferentes piezas que hemos visto puedes hacer otros proyectos.

En este proyecto queremos simular el funcionamiento real de un rover :

* Mover de forma remota el rover controlando paso a paso su posición.
* Mover el brazo robótico
* Ver la cámara

Luego juntamos 3 piezas del puzzle:

* [Movimientos paso a paso con las teclas](/35-m2-movimientos-con-paso.md)
* [Movimiento brazo robótico](/6-servos/72-test-brazo.md)
* [Cámara](/8-camara/84-ver-la-camara.md)

## Resultado 🛰

{% youtube %}https://www.youtube.com/watch?v=plpvaGh7otw&feature=youtu.be{% endyoutube %}

... vale, vale, no es Marte 🪐, son los bajos de mi coche aquí en la Tierra 🌍.

## ¿Cómo se hace?

¿Te atreves?

%accordion%Solución%accordion%

* El proyecto es fácil pues es la unión de [Movimientos paso a paso con las teclas](/35-m2-movimientos-con-paso.md) y [Movimiento brazo robótico](/6-servos/72-test-brazo.md)
* Ver la cámara no implica ningún código Python especial, si está bien configurado, sólo es abrir una pantalla de tu navegador con la dirección URL adecuada.

Fichero [BajosCoche.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

from VARIABLES import *

import BRAZO
import MOVIMIENTOS
import MOVIMIENTOSPASO


velR=30
numR=10
velL=30
numL=10

angulox=90
anguloz=90
incremento=20
print("Teclas 8 y 2 SERVOX\n Teclas 4 y 6 SERVOZ")
print ('TECLAS ¡en minúscula!:\nADELANTE=FORDWARD = f\nATRAS=BACKWARD = b\nDERECHA=RIGHT = r\nIZQUIERDA=LEFT = l')
tecla='x'

print ('Mira la cámara en http://192.168.1.25:8080')

while True:
    BRAZO.ANGULO(angulox,1)
    BRAZO.ANGULO(anguloz,0)
    tecla=input("Mueve el brazo o movimiento: ")
    if (tecla=="8"):
        angulox=angulox-incremento
    if (tecla=="2"):
        angulox=angulox+incremento
    if (tecla=="4"):
        anguloz=anguloz+incremento
    if (tecla=="6"):
        anguloz=anguloz-incremento
    if tecla=='f':
        print ('\nadelante')
        MOVIMIENTOSPASO.BOTH(velR,numR,velL,numL)
    if tecla=='b':
        print ('\natrás')
        MOVIMIENTOSPASO.BOTH(velR,-numR,velL,-numL)
    if tecla=='r':
        print ('\nderecha')
        MOVIMIENTOSPASO.BOTH(velR,-numR,velL,numL)
    if tecla=='l':
        print ('\nizquierda')
        MOVIMIENTOSPASO.BOTH(velR,numR,velL,-numL)


```
%/accordion%
