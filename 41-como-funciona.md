#¿Cómo funciona el sensor de obstáculos infrarrojo?

Lo primero que tenemos que hacer es ajustar su sensibilidad con el potenciómetro que tiene de tal manera que detecte de forma correcta un obstáculo:

{% youtube %}https://www.youtube.com/watch?v=_89J0WtOqgQ&feature=youtu.be{% endyoutube %}

ES MUY SENSIBLE el punto está justo cuando se apaga:

![](/assets/sensorIRObstaculos2.png)

{% youtube %}https://www.youtube.com/watch?v=aJonvDOttgU&feature=youtu.be{% endyoutube %}

Tiene un led de infrarrojos que cuando hay un obstáculo delante del sensor, refleja esta radiacción y el otro LED (realmente no se podría decir que es LED pues no emite, se tendría que llamar unión PN semiconductor), es un sensor receptor que lo detecta. Un chip comparador LM393 detecta la señal y su sensibilidad se ajusta con el potenciómetro:

![](/assets/sensorIRObstaculos3.png)

La salida DOUT de cada LM393 están conectados a los siguientes puertos GPIO:

* Derecha GPIO 16
* Izquierda GPIO 19

Una vez más vemos que la resistencias del sensor están tipo PULL-UP luego cuando detecta emitirá un 0 lógico y cuando no detecta emitirá un 1 lógico.