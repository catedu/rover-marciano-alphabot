# Módulo siguelíneas

## ORBITAS

Esta claro que un rover de verdad no va a tener que seguir una línea pintada en el suelo. Pero, las sondas que lo transportan a los astros, sí que tiene que seguir  unas órbitas o líneas imaginarias. Nosotros lo vamos a simular con una línea pintada en el suelo.

La programación básica es la misma siempre: si te desvías, corrige.

![](/assets/orbita.gif)

[Philae rover's orbit in comet 67P](https://www.popularmechanics.com/space/g2874/nasa-giphy-page/)

Pero no es fácil elegir la órbita :

{% youtube %}https://www.youtube.com/watch?v=gYJsMBabjVY&list=PL9TFrgFq7557nWqmfuVngU22OhTpUE9gg&index=2{% endyoutube %}

## NUESTRO ROBOT SIGUELINEAS

Nuestro robot tiene un módulo con 5 sensores al color :

![](/assets/siguelineas.jpg)

Tiene un funcionamiento similar al [Sensor obstáculos IR](/4-sensor-obstaculos-ir.md). El receptor tiene un sensor de reflexión de infrarrojos ITR20001/T. Un led emite luz IR contínuamente, la luz infraroja es reflejado por un obstáculo y lo recibe el receptor.

La salida del sensor es analógica y es sensible al color y la distancia del objeto detectado.

Tiene 5 canales de sensores. Chequeandolos se puede juzgar la posición de la línea oscura que esté en el suelo.

![](/assets/siguelineas2.jpg)
