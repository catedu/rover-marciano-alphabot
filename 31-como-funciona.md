#Cómo funciona el sensor de velocidad

El WYC-H206 es un diodo emisor de IR por una parte y por otra es un sensor fotoeléctrico, que detecta los agujeros que hay enmedio de los dos, pasando por un pequeño adaptador 74x126 que adapta la señal para ser leida apropiadamente:

![](/assets/esquemasensorvelocidad.jpg)

Están conectados a los siguientes GPIO:
* Motor derecha GPIO7
* Motor izquierda GPIO8

![](/assets/motoressensorvelocidad.jpg)

Si te fijas en el esquema anterior, las resistencias, están con la configuración **PULL-UP** ([aquí para saber +](https://catedu.github.io/programa-arduino-mediante-codigo/resistencias_pullup_y_pulldown.html) en el curso Arduino) ¿qué significa esto? pues que van al revés, cuando el circuito está encendido, o sea detecta agujero, estado ON transmite un 0 lógico, y al revés, cuando está apagado OFF transmite un 1 lógico, lo puedes ver mejor en estas fotografías, midiendo con un tester entre masa y el pin 8 BCM (pues es la rueda izquierda) o pin 24 del conector [ver GPIO](https://catedu.github.io/rover-marciano-alphabot/gpio.html) :

![](/assets/sensorvelocidadOFF.jpg)
![](/assets/sensorvelocidadON.jpg)
