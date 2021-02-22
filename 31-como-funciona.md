#Cómo funciona el sensor de velocidad

Las ruedas tienen un disco con agujeros, una parte es un diodo emisor de IR y el otro es un sensor fotoeléctrico tipo WYC-H206 que detecta los agujeros:

![](/assets/esquemasensorvelocidad.jpg) 

Están conectados a los siguientes GPIO:
* Motor derecha GPIO7
* Motor izquierda GPIO8

![](/assets/motoressensorvelocidad.jpg)

Si te fijas en el esquema anterior, las resistencias, están con la configuración **PULL-UP** ([aquí para saber +](https://catedu.github.io/programa-arduino-mediante-codigo/resistencias_pullup_y_pulldown.html) en el curso Arduino) ¿qué significa esto? pues que van al revés, cuando el circuito está encendido, o sea detecta agujero, estado ON transmite un 0 lógico, y al revés, cuando está apagado OFF transmite un 1 lógico, lo puedes ver mejor en estas fotografías:

![](/assets/sensorvelocidadOFF.jpg)
![](/assets/sensorvelocidadON.jpg)


