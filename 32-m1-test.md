#Un primer test del sensor de velocidad

En el siguiente vídeo vemos como cuando el sensor está encendido, el programa detecta un 0 y si el sensor está apagado, el programa detecta un 1:

{% youtube %}https://www.youtube.com/watch?v=anWM7Y54u98&feature=youtu.be{% endyoutube%}

Fichero [Pruebasensorvelocidad.py](https://github.com/JavierQuintana/AlphabotPython/)

El programa es el siguiente:
```cpp+lineNumbers:true
import RPi.GPIO as GPIO

DataMotorR = 7
DataMotorL = 8

GPIO.setmode(GPIO.BCM)

GPIO.setup(DataMotorR,GPIO.IN)
GPIO.setup(DataMotorL,GPIO.IN)


for i in range(100000):
    print('\nMotor derecha   :',GPIO.input(DataMotorR))
    print('\nMotor izquierda :',GPIO.input(DataMotorL))
```
## Segundo test de contador
En el segundo vídeo vídeo vemos como un simple contador puede detectar el paso del 1 al 0:

{% youtube %}https://www.youtube.com/watch?v=Xm1aZvEp9fE&feature=youtu.be{% endyoutube%}


El programa es el siguiente:

Fichero [Pruebasensorvelocidad-2.py](https://github.com/JavierQuintana/AlphabotPython/)

```cpp+lineNumbers:true

import RPi.GPIO as GPIO

DataMotorR = 7
DataMotorL = 8

GPIO.setmode(GPIO.BCM)

GPIO.setup(DataMotorR,GPIO.IN)
GPIO.setup(DataMotorL,GPIO.IN)

contador=0
repetido=0
num = 100
while (contador<num):
    if((GPIO.input(DataMotorR)==1)and(repetido==0)):
        contador=contador+1
        print('\nContador :',contador)
        repetido=1
    if(GPIO.input(DataMotorR)==0):
        repetido=0
```