##Añadimos más variables a VARIABLES.py
Los marcados en negrita:
<hr />
import RPi.GPIO as GPIO
###########MOTORES
IN1=12
IN2=13
ENA=6
IN3=20
IN4=21
ENB=26
########SENSOR VELOCIDAD MOTORES
DataMotorR = 7
DataMotorL = 8

**##########SENSOR OBSTACULOS IR
DR = 16
DL = 19**

##############CONFIGURACION GPIO ENTRADAS SALIDAS ####
GPIO.setmode(GPIO.BCM)
GPIO.setwarnings(False)
#########################MOTORES
GPIO.setup(IN1,GPIO.OUT)
GPIO.setup(IN2,GPIO.OUT)
GPIO.setup(IN3,GPIO.OUT)
GPIO.setup(IN4,GPIO.OUT)
GPIO.setup(ENA,GPIO.OUT)
GPIO.setup(ENB,GPIO.OUT)
#################### VELOCIDAD DE LOS MOTORES
PWMA = GPIO.PWM(ENA,500)
PWMB = GPIO.PWM(ENB,500)
##################SENSOR VELOCIDAD MOTORES
GPIO.setup(DataMotorR,GPIO.IN)
GPIO.setup(DataMotorL,GPIO.IN)

**####################SENSORES OBSTACULOS IR
GPIO.setup(DR,GPIO.IN)
GPIO.setup(DL,GPIO.IN)**




