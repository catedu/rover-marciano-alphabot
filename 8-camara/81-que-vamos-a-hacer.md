#¿Qué vamos a hacer?

Manejar la cámara web es fácil si queremos que salga por la salida HDMI de la Raspberry, simplemente ejecutando el siguiente código Python sale, en este caso durante 10 segundos **Pero no sale por VNC ni por SSH**:
```cpp+lineNumbers:true
from picamera import PiCamera
from time import sleep
camera = PiCamera()
camera.start_preview()
sleep(10)
camera.stop_preview()
```
Pero nosotros necesitamos que **retransmita = streaming** las imágenes, pues el robot se mueve, no tiene instalado un monitor.

Encontrarás en Internet varias formas de hacerlo:

1. Utilizando un programa en Python
1. Utilizando MJPG STREAMER bajo un programa servidor WEBIOPI
1. Utilizando **Motion** (recomendamos)

La primera opción [video](https://www.youtube.com/watch?v=fCTc1sBQwi8) o [este tutorial](https://randomnerdtutorials.com/video-streaming-with-raspberry-pi-camera/) dependes de tener todas las librerías intaladas, por ejemplo *limmal* ...

La segunda opción WEBIOPI (http://webiopi.trouch.com/) siguen con la versión 0.7.1 sin actualizar luego no lo recomendamos

Vamos a usar **Motion**, un programa diseñado para manejar la cámara en estos contextos y sí que está actualizado (actualmente por la 4.3.1) y muy extendido en el uso de cámaras web, lo que nos da unas garantías de no tener problemas, su página web oficial https://motion-project.github.io/index.html .
