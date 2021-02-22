# VARIABLES.py

En Alphabot el servo de abajo del brazo robot \(lo llamaremos eje z por ser el responsable del giro del eje vertical\) está conectado al GPIO 27 y el servo de arriba \(lo llamaremos x\) al GPIO 22 luego añadiremos estas líneas en nuestro fichero VARIABLES.py. Lo configuramos como salida y que inicialmente esten no activos para que no se mueva el brazo en el comienzo:

###### \#\#\#\# SERVOS BRAZO ROBOT

SERVOEJEX = 22

SERVOEJEZ = 27

###### \#\#\#\#\#\#\# SERVOS BRAZO ROBOT

GPIO.setup\(SERVOEJEX, GPIO.OUT, initial=GPIO.LOW\)

GPIO.setup\(SERVOEJEZ, GPIO.OUT, initial=GPIO.LOW\)

# BRAZO.py

Realmente el control de un servo se hace con una modulación PWM que ya hemos visto. La función que modula la señal PWM es ChangeDutyCycle y se le da el argumento en % entre 0 y 100. Si queremos 180º necesitamos un pulso de 2.5ms por lo que en 20ms corresponde a 12.5% por lo tanto la fórmula es % = 2.5+10\*\(angulo/180\):

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time

from VARIABLES import *

servox = GPIO.PWM(SERVOEJEX,40)
servoz = GPIO.PWM(SERVOEJEZ,40)
servox.start(0)
servoz.start(0)

def ANGULO(angle,x):
    if (x):
        servox.ChangeDutyCycle(2.5 + 10.0 * angle / 180)
    else:
        servoz.ChangeDutyCycle(2.5 + 10.0 * angle / 180)
```

>Nota: Los servos tiemblan algo, es normal, no pienses que un robot barato esté bien calibrado.

