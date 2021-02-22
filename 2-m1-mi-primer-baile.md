#M1 Mi primer baile

Vamos a realizar un sencillo programa para romper el hielo, unos movimientos delante, atrás, derecha, izquierda y paro utilizando la librería anterior:

{% youtube %}https://www.youtube.com/watch?v=WAycuDaKB0Q{% endyoutube%}


##Solución
* Ponemos el fichero MOVIMIENTOS.py [que hemos visto](/24-libreria-movimientospy.md) en la misma carpeta que vamos a crear este programa.
* En este programa importamos la librería de MOVIMIENTOS.py.
* Vamos llamando a las distintas funciones de movimientos, fijamos la velocidad al 50%, insertando entre ellas un tiempo de retraso de la librería time de 1 segundo.

¿Te atreves? Sino, mira la solución:

%accordion%Solución%accordion%

Fichero [2-6-Baile.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

import MOVIMIENTOS

MOVIMIENTOS.FORDWARD(50)
time.sleep(1)
MOVIMIENTOS.BACKWARD(50)
time.sleep(1)
MOVIMIENTOS.LEFT(50)
time.sleep(1)
MOVIMIENTOS.RIGHT(50)
time.sleep(1)
MOVIMIENTOS.STOP()
```
%/accordion%


