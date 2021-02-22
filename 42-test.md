#Test sensor obstáculos infrarrojos
Ejecutamos este pequeño programa:

Fichero [4-2-TestObstaculoIR.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

DR = 16
DL = 19

GPIO.setmode(GPIO.BCM)

GPIO.setup(DR,GPIO.IN)
GPIO.setup(DL,GPIO.IN)

for i in range(10000):
     print('\nSensor derecha :',GPIO.input(DR))
     print('\nSensor izquier :',GPIO.input(DL))
```

Y podemos ver en el vídeo que emite un 0 cuando detecta un obstáculo:

{% youtube %}https://www.youtube.com/watch?v=oehMTYNSPHA&feature=youtu.be{% endyoutube %}