#Ver la cámara
###Arrancar MJPG-STREAMER
Entrar en el directorio donde esta mjpeg-streamer, abrimos una terminal con el botón derecho en esa carpeta y tecleamos:

>sudo ./start.sh

sale lo siguiente:

![](/assets/mjpeg3.jpg)

###Stream
Desde un ordenador conectado en la misma wifi que la raspberry entramos en la siguiente dirección http://ip_de_la_rasberry:8080/ por ejemplo http://192.168.1.25:8080/ y vemos lo siguiente:

![](/assets/mjpeg4.jpg)

Entramos en Stream y tachán !!!

![](/assets/mjpeg5.jpg)

Si sólo quieres ver la cámara http://ip_de_la_rasberry:8080/?action=stream.

#####¿Problemas?
* Funciona la página MJPG-Streamer pero la cámara no se ve: 
En esta [página ](https://www.raspberrypi.org/forums/viewtopic.php?t=100818)encontré la solución.

###Truco
Instálate [VLC](https://www.videolan.org) y copia la dirección que sale en la página VideoLAN en VLC-Medio-Abrir ubicación de red ... - red y pega esa dirección

![](/assets/mjpgporvlc.jpg)



