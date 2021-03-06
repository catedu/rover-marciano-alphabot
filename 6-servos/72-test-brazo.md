#Test brazo robotico
Vamos a realizar una función que controle con el teclado el brazo robótico, si le pusieramos [un diodo laser](https://www.amazon.es/WPERSUVV-m%C3%B3dulos-creaci%C3%B3n-prototipos-Raspberry/dp/B07RM3RWSF/ref=sr_1_1_sspa?dchild=1&keywords=laser+diodo+arduino&qid=1615466315&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFUWVVaMUQ3WldCSDQmZW5jcnlwdGVkSWQ9QTAzMTIzNTlVNDRRNlE2Wk1OQjQmZW5jcnlwdGVkQWRJZD1BMDIyMjI4NDJEWEtWSFpMWDRPS1gmd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl), podriamos incluso imitar al vaporizador que esta montado en la Perserverante:

![](/assets/curiosity-laser.gif)

[NASA's Mars Curiosity rover landed on Mars in 2012. NASA/JPL-Caltech](https://mars.nasa.gov/msl/home/)

De momento nos vamos a conformar con hacer esto :

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
