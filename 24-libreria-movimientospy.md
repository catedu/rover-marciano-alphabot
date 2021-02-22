#Librería MOVIMIENTOS.py

Para simplificar nuestros programas podemos hacer una librería propia.

Esta librería la vamos a llamar **[MOVIMIENTOS.py](https://github.com/JavierQuintana/AlphabotPython/)** y su contenido sería lo visto en las páginas anteriores, añadiendo las variables definidas en **VARIABLES.py**:

```cpp+lineNumbers:true
import RPi.GPIO as GPIO

from VARIABLES import *


###########################FUNCIONES#######################
def FORDWARD(vel):
    GPIO.output(IN1,GPIO.HIGH)
    GPIO.output(IN2,GPIO.LOW)
    GPIO.output(IN3,GPIO.LOW)
    GPIO.output(IN4,GPIO.HIGH)
    PWMA.start(vel)
    PWMB.start(vel)

def BACKWARD(vel):
    GPIO.output(IN1,GPIO.LOW)
    GPIO.output(IN2,GPIO.HIGH)
    GPIO.output(IN3,GPIO.HIGH)
    GPIO.output(IN4,GPIO.LOW)
    PWMA.start(vel)
    PWMB.start(vel)

def LEFT(vel):
    GPIO.output(IN1,GPIO.LOW)
    GPIO.output(IN2,GPIO.LOW)
    GPIO.output(IN3,GPIO.LOW)
    GPIO.output(IN4,GPIO.HIGH)
    PWMA.start(vel)
    PWMB.start(vel)

def RIGHT(vel):
    GPIO.output(IN1,GPIO.HIGH)
    GPIO.output(IN2,GPIO.LOW)
    GPIO.output(IN3,GPIO.LOW)
    GPIO.output(IN4,GPIO.LOW)
    PWMA.start(vel)
    PWMB.start(vel)

def STOP():
    GPIO.output(IN1,GPIO.LOW)
    GPIO.output(IN2,GPIO.LOW)
    GPIO.output(IN3,GPIO.LOW)
    GPIO.output(IN4,GPIO.LOW)
```