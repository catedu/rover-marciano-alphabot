#Añadimos a Fichero VARIABLES.py

Añadimos ahora las varialbes de paso siguientes a este fichero

[VARIABLES.py](https://github.com/JavierQuintana/AlphabotPython/blob/master/VARIABLES.py)

import RPi.GPIO as GPIO

**DataMotorR = 7
DataMotorL = 8**

IN1=12
IN2=13
ENA=6
IN3=20
IN4=21
ENB=26

##############CONFIGURACION GPIO ENTRADAS SALIDAS ####
GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)
GPIO.setup(IN1,GPIO.OUT)
GPIO.setup(IN2,GPIO.OUT)
GPIO.setup(IN3,GPIO.OUT)
GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT)
GPIO.setup(ENB,GPIO.OUT)

**GPIO.setup(DataMotorR,GPIO.IN)
GPIO.setup(DataMotorL,GPIO.IN)
**

########################### VELOCIDAD DE LOS MOTORES
PWMA = GPIO.PWM(ENA,500)
PWMB = GPIO.PWM(ENB,500)
```

