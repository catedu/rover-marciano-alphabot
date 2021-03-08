# GPIO y PYTHON

## GPIO

Vamos a recordar lo que vimos [aquí](https://catedu.github.io/raspberry-muy-basico/2-gpio.html), dos cosas:

* Estos son los pines GPIO con la numeración BCM:

![](https://docs.microsoft.com/en-us/windows/iot-core/media/pinmappingsrpi/rp2_pinout.png)

* Están diseñados para 3.3V sólo proporcionan 3mA cada pin luego NO conectes diréctamente componentes de 5V ni  que consuman más corriente o de lo contrario ESTROPEARÁS LA RASPBERRY DE FORMA IRREVERSIBLE, o sea, directamente sólo LEDs con una resistencia de mínimo 1.1K tal [y como vimos aqui](https://catedu.github.io/raspberry-muy-basico/2-gpio.html), todo lo demás a través de chips drivers, por eso utilizamos este kit comercial.

En nuestro rover la conexión es la siguiente:

![](/assets/gpy.jpg)

## Librería RPI.GPIO

Necesitamos una librería GPIO que Raspbian lo tiene por defecto, pero por si acaso ejecuta estas instrucciones:

> sudo apt-get install python-dev
>
> sudo apt-get install pyton-rpi.gpio

Normalmente te dirá que las tienes instaladas en su última versión.  
Para utlizar la librería, simplemente tenemos que poner esta instrucción:  
**import RPi.GPIO as GPIO**

## GPIO.setmode y GPI.setup

Hay dos formas de utilizar la numeración de las GPIO, respetando la misma numeración que los pines de la placa, entonces la instrucción que tenemos que poner en nuestros programas es:  
**GPIO.setmode\(GPIO.BOARD\)**  
o utilización de la numeración BCM:  
**GPIO.setmode\(GPIO.BCM\)**  
nosotros elegiremos esta última por ser más sencilla, aunque tiene la desventaja de que si cambian en el futuro la numeraciones en los BCM nuestro programa no servirá.

Una vez definido qué numeración usamos, tenemos que especificar en nuestro programa si tal GPIO es entrada o salida, por ejemplo la siguiente instrucción define el GPIO número 4 como entrada \(7 en numeración BOARD\):  
**GPIO.setup\(4, GPIO.IN\)**

## ¿Qué es lo que hay conectado en cada puerto GPIO de este rover?

Pues aquí lo tienes, cada uno lo vamos a ver a lo largo de este curso :

| Interfaces | Puertos GPIO de la Raspberry Pi nomenclatura BCM |
|------------|--------------|
|   IN1 motores     | 12          |
|   IN2  motores    | 13          |
|   ENA  motores    | 6           |
|   IN3  motores    | 20          |
|   IN4    motores  | 21          |
|   ENB    motores  | 26          |
| Sensor velocidad derecha | 7 |
| Sensor velocidad izquierda | 8 |
| Sensor IR obstáculos derecha | 16 |
| Sensor IR obstáculos izquierda | 19 |
| Sensor IR mando distancia | 18 |
| Siguelineas CS | 5 |
| Siguelíneas Clock | 25 |
| Siguelíneas Address | 24 |
| Siguelíneas DataOut | 23 |
| Servo brazo eje X | 22 |
| Servo brazo eje Z | 27 |


## Ejemplo de utilización de la librería RPI.GPIO

El siguiente ejemplo enciende un LED puesto en el GPIO 4, durante 2 segundos

```cpp+lineNumbers:true
import RPi.GPIO as GPIO
import time
GPIO.setmode(GPIO.BCM)
GPIO.setup(4, GPIO.OUT) ## GPIO 4 como salida
GPIO.output(4,True) ##encendemos
time.sleep(2)        ## espera 2 segundos
GPIO.output(4,False)  ##APAGAMOS
```
**No lo hagas** pues en el 4 de este rover no hay puesto nada, mira el [plano esquemático](https://www.waveshare.com/w/upload/b/b1/AlphaBot_Schematic.pdf) y en P4 (pin 7 real del conector RPI1) no hay nada conectado.

![](/assets/gpy.jpg)
