#Una señal especial: PWM
###¿Qué es?
Para entender el funcionamiento de los motores, primero tenemos que hablar de esta señal especial.

La RASPBERRY igual que el ARDUINO ([ver cap 2.4 curso Arduino](https://catedu.github.io/programa-arduino-mediante-codigo/un_caso_especial_seales_pwm.html)) no es capaz de generar señales ANALÓGICAS. Un truco es generar una señal cuadrada de pulsación variable PWM (Pulse Width Modulation, Modulación de Ancho de Pulso) de esta forma "simula" una señal analógica.

![](https://catedu.github.io/programa-arduino-mediante-codigo/img/Captura_de_pantalla_2015-05-19_a_las_14.18.40.png)

##¿Cómo se genera utilizando PYTHON y los pines GPIO?

Se realiza primero creando una variable especial PWM con la instrucción:

**p = GPIO.PWM(canal, frecuencia)** donde canal es el número de pin GPIO donde queremos generar la señal PWM de frecuencia dada en Hz

Con esto está creado pero no genera los pulsos, para eso se hace con la instrucción:

**p.start(dc) **donde dc=duty cycle en % es decir desde 0.0 hasta 100.0, por ejemplo en la figura anterior, la a) sería dc=25 el b) dc=50 y la gráfica c) sería un dc=75.

Para parar **p.stop()**

##Please! ¿Un ejemplo?
Claro, vamos a ver un ejemplo sencillo que es encender un LED  cada 2 segundos en el GPIO número 12:

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
GPIO.setmode(GPIO.BOARD)
GPIO.setup(12, GPIO.OUT)  #definimos el GPIO12 como salida

p = GPIO.PWM(12, 0.5)
p.start(50)

```


