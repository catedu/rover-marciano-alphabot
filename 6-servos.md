#SERVOS

Los servos son motores con una reductora, un sensor de posición y un circuito de control del ángulo de giro. Son utilizados en los brazos robóticos y como puedes ver  **juegan un importante papel en los rovers** por ejemplo en el actual Perseverance :

<iframe src="https://mars.nasa.gov/layout/embed/video/?v=423" width="640" height="370" scrolling="no" frameborder="0"></iframe>

Para saber más de servos te recomendamos el [capítulo de servomotores del curso de Arduino de Aularagón.](https://catedu.github.io/programa-arduino-mediante-codigo/control_de_servomotores.html).

Los que tiene nuestro rover son más baratos:

![](/assets/servo.jpg)

Tiene 3 cables:

* Marrón a GND
* Naranja a 5V
* Rojo la señal de control

La señal de control tiene que emitir un pulso alto durante un intervalo de al menos 20mseg, que según su duración en estado alto, se traduce en un ángulo de rotación del servo:

![](/assets/servo2.jpg)

![](http://picmania.garcia-cuervo.net/images/servo_pulsos_pwm.jpg)
