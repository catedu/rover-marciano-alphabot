#SERVOS

![](/assets/servo.jpg)

Los servos son motores con una reductora, un sensor de posición y un circuito de control del ángulo de giro. Para saber más de servos te recomendamos el [capítulo de servomotores del curso de Arduino de Aularagón.](https://catedu.github.io/programa-arduino-mediante-codigo/control_de_servomotores.html).

Tiene 3 cables:
* Marrón a GND
* Naranja a 5V
* Rojo la señal de control

La señal de control tiene que emitir un pulso alto durante un intervalo de al menos 20mseg, que según su duración en estado alto, se traduce en un ángulo de rotación del servo:

![](/assets/servo2.jpg)

![](http://picmania.garcia-cuervo.net/images/servo_pulsos_pwm.jpg)

