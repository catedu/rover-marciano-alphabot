#Movimientos con paso y teclas

Vamos a hacer un programa para utilizar la librería anterior MOVIMIENTOSPASO.py y gobernado por el teclado *numérico*:

* PARAR = tecla 5
* ADELANTE=FORDWARD = 8
* ATRAS=BACKWARD = 2
* DERECHA=RIGHT = 6
* IZQUIERDA=LEFT = 4

Fijaremos de antemano las velocidades y el paso a 50 y 10 por ejemplo.

{% youtube %}https://www.youtube.com/watch?v=n0tOHIHl0Rs&feature=youtu.be{% endyoutube %}
####Solución
* Ponemos las librerías fichero [MOVIMIENTOS.py](/24-libreria-movimientospy.md) y [MOVIMIENTOSPASO.py](/34-movimientospasopy.md) en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* Vamos llamando a las distintas funciones de movimientos según la tecla pulsada, fijamos la velocidad al 50%, por pantalla va saliendo el estado de los contadores.
* Todo dentro de un bucle de manera que si pulsamos la tecla espacio sale del buble no sin antes parar el robot.

%accordion%Solución%accordion%

Fichero [3-5-Movimientos-paso.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

import MOVIMIENTOS
import MOVIMIENTOSPASO

velR=50
numR=10
velL=50

numL=10

print ('TECLAS ¡en minúscula!:\nPARAR = tecla 5\nADELANTE=FORDWARD = 8\nATRAS=BACKWARD = 2\nDERECHA=RIGHT = 6\nIZQUIERDA=LEFT = 4')
tecla='x' 
while tecla!='5':
    tecla = input('\nPresiona una tecla y después enter : ')
    if tecla != '5':
        print ('\nHas presionado ', tecla)
        if tecla=='8':
            print ('\nadelante')
            MOVIMIENTOSPASO.BOTH(velR,numR,velL,numL)
        if tecla=='2':
            print ('\natrás')
            MOVIMIENTOSPASO.BOTH(velR,-numR,velL,-numL)
        if tecla=='6':
            print ('\nderecha')
            MOVIMIENTOSPASO.BOTH(velR,-numR,velL,numL)
        if tecla=='4':
            print ('\nizquierda')
            MOVIMIENTOSPASO.BOTH(velR,numR,velL,-numL)

    else:
        print ('\nFin, has apretado STOP')
        MOVIMIENTOS.STOP()
```
%/accordion%


