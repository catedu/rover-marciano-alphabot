#Roomba o sea "Evita obstáculos"

Bueno ahora hay que hacer el típico programa que evite los obstáculos. Ya sabes detectar los obstáculos, ya sabes controlar el movimiento ¿a qué esperas?

<iframe src="https://giphy.com/embed/kviKlWqjoBdCw" width="480" height="319" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/adventure-roomba-kviKlWqjoBdCw">via GIPHY</a></p>

{% youtube %}https://www.youtube.com/watch?v=5LvBqHv1wM4&feature=youtu.be{% endyoutube %}

####Solución
La solución no es única, una propuesta es hacerlo con las librerías que hemos aprendido:
* Ponemos las librerías fichero [MOVIMIENTOS.py](/24-libreria-movimientospy.md) y [MOVIMIENTOSPASO.py](/34-movimientospasopy.md) en la misma carpeta que vamos a crear este programa y las incorporamos en el programa con **import**.
* También incorporamos las variables definidas en **VARIABLES.py**
* Si no detecta nada, que sigua hacia delante.
* Si detecta algo, según los dos o uno, que de unos pasos atrás y que gire.

%accordion%Solución%accordion%

Fichero [Roomba.py](https://github.com/JavierQuintana/AlphabotPython/)
```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time
from VARIABLES import *
import MOVIMIENTOS
import MOVIMIENTOSPASO

while True:
    sensorR= not (GPIO.input(DR))
    sensorL= not (GPIO.input(DR))
    if not(sensorR and sensorL):
         MOVIMIENTOS.FORDWARD(50)
    if (sensorR and sensorL):
        MOVIMIENTOSPASO.BOTH(50,-10,50,-10)
    if (sensorR and not(sensorL)):
        MOVIMIENTOSPASO.BOTH(50,-5,50,-5)
        MOVIMIENTOSPASO.BOTH(40,-5,40,5)
    if (not(sensorR) and (sensorL)):
        MOVIMIENTOSPASO.BOTH(50,-5,50,-5)
        MOVIMIENTOSPASO.BOTH(40,5,40,-5)    
        
```
%/accordion%
    
    
    

