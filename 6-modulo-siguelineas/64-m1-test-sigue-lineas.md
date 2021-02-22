#Test Siguelineas
Podemos hacer un test para ver cómo funciona este siguelíneas y cómo funciona la librería

* Importamos la librería [TLC1543 creada anteriormente](/6-modulo-siguelineas/tlc1543py.md)
* Vamos leyendo cada uno de los sensores.
* Que salga por pantalla los valores leídos.

{% youtube %}https://www.youtube.com/watch?v=MFWnOyL_nzU&feature=youtu.be{% endyoutube %}
¿Te atreves?:

%accordion%Solución%accordion%

Fichero [Testsiguelineas.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true

import RPi.GPIO as GPIO
import time

import TLC1543
 
while True:
    for i in range(5):
        x=TLC1543.SENSORLINEA(i)
        print (" Sensor",i,"= ",x,end="")
    print(" ");
    time.sleep(0.5)
```

%/accordion%

