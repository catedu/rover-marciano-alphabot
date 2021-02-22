#Test brazo robotico
Vamos a realizar una función que controle con el teclado el brazo robótico:
* Teclas 8 y 2 mueven el brazo robot en el eje x arriba y abajo
* Teclas 4 y 6 mueven el brazo robot en el eje z derecha e izquierda.

Fijaremos de antemano un incremento de 10ª cada vez que pulsamos la tecla. Veamoslo con un vídeo:

{% youtube %}https://www.youtube.com/watch?v=S3Z9vRjPtQo&feature=youtu.be{% endyoutube %}
####Solución
* Ponemos la librería del fichero BRAZO.py en la misma carpeta que vamos a crear este programa y la incorporamos en el programa con **import**.
* Importamos las variables también con import * from VARIABLES
* Vamos incrementando los ángulos eje x y eje z según la tecla pulsada.
* Todo dentro de un bucle.

¿Te atreves? :

%accordion%Solución%accordion%

Fichero [Test-Brazo.py](https://github.com/JavierQuintana/AlphabotPython/)
```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

from VARIABLES import *

import BRAZO

angulox=90
anguloz=90
incremento=20
print("Teclas 8 y 2 SERVOX\n Teclas 4 y 6 SERVOZ")
while True:
    BRAZO.ANGULO(angulox,1)
    BRAZO.ANGULO(anguloz,0)
    tecla=input("Mueve el brazo : ")
    if (tecla=="8"):
        angulox=angulox-incremento
    if (tecla=="2"):
        angulox=angulox+incremento
    if (tecla=="4"):
        anguloz=anguloz+incremento
    if (tecla=="6"):
        anguloz=anguloz-incremento
```
%/accordion%

