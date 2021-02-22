#Movimientos con teclas
Ahora vamos a hacer lo mismo, pero gobernado por el teclado:

* PARAR = tecla ESPACIO
* ADELANTE=FORDWARD = f
* ATRAS=BACKWARD = b
* DERECHA=RIGHT = r
* IZQUIERDA=LEFT = l

{% youtube %}https://www.youtube.com/watch?v=fb6w5yQB_AM&feature=youtu.be{% endyoutube%}

###Solución
* Ponemos el fichero MOVIMIENTOS.py [que hemos visto](/24-libreria-movimientospy.md) en la misma carpeta que vamos a crear este programa.
* En este programa importamos la librería de MOVIMIENTOS.py.
* Vamos llamando a las distintas funciones de movimientos según la tecla pulsada, fijamos la velocidad al 30% para que nos de tiempo de gobernarlo, por pantalla va saliendo el mensaje del estado.
* Todo dentro de un bucle de manera que si pulsamos la tecla espacio sale del buble no sin antes parar el robot.

¿Te atreves a hacerlo tú solo? sino, mira la solución:

%accordion%Solución%accordion%

Fichero [2-7-Movimientos-Teclas.py](https://github.com/JavierQuintana/AlphabotPython/)
```cpp+lineNumbers:true

import RPi.GPIO as GPIO
import time

import MOVIMIENTOS

print ('TECLAS ¡en minúscula!:\nPARAR = tecla ESPACIO\nADELANTE=FORDWARD = f\nATRAS=BACKWARD = b\nDERECHA=RIGHT = r\nIZQUIERDA=LEFT = l')
tecla='x' 
while tecla!=' ':
    tecla = input('\nPresiona una tecla y después enter : ')
    if tecla != ' ':
        print ('\nHas presionado ', tecla)
        if tecla=='f':
            print ('\nadelante')
            MOVIMIENTOS.FORDWARD(30)
        if tecla=='b':
            print ('\natrás')
            MOVIMIENTOS.BACKWARD(30)
        if tecla=='r':
            print ('\nderecha')
            MOVIMIENTOS.RIGHT(30)
        if tecla=='l':
            print ('\nizquierda')
            MOVIMIENTOS.LEFT(30)
            
    else:
        print ('\nFin, has apretado STOP')
        MOVIMIENTOS.STOP()
```
%/accordion%


