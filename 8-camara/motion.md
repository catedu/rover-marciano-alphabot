
#8.6 Ver la cámara de la Raspberry desde Internet

##8.6.1 Pasos previos
Tenemos que realizar los siguientes pasos:

1. Registrarse en un servicio de Dominio Virtual, por ejemplo Remote.it
1. Instalar el servicio SSH
1. Instalar el servicio VNC
1. Acceder a nuestra Raspberry por SSH y VNC desde Internet

Todos los pasos están explicados en [este enlace](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet.html). 

Al manejar nuestra Raspberry por VNC y/o SSH desde Internet, podemos controlar nuestro Alphabot desde cualquier lugar del mundo !!! ¡¡no es alucinante !!

<iframe src="https://giphy.com/embed/rWzfEEku6SovK" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/rWzfEEku6SovK">via GIPHY</a></p>

Vale, vale, ya veo que no es para tanto...

##8.6.2 Instalar el servicio HTTP puerto 8000 para ver WebIOPi

Si has instalado el servicio SSH y VNC tal y como dice [aquí](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet/112-instalar-remoteit-en-la-raspberry.html), encontes tienes intalado en la Raspberry weavedconnectd por lo tanto , lo que tenemos que hacer es ejecutarlo:

>sudo weavedinstaller

Nos aparecerá un menú, elegiremos la opción 1 (aunque las otras también podrían valer pero lo más fácil es registrarse online tal y como hemos visto [aquí](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet/111-remoteit.html) y utilizar ese usuario y contraseña con la opción 1):

![](http://forum.weaved.com/uploads/default/original/1X/415af66ac614261c254f11b540f0dd34297998f3.png)

Aparecerá este menú

![](https://catedu.github.io/raspberry-muy-basico/assets/pi@raspberrypi_%20~.jpg)

Elegimos la opción 1 y del siguiente menú

![](https://catedu.github.io/raspberry-muy-basico/assets/otromenu.jpg)

La opción 2 pero por defecto te pondrá el puerto 80, **cambialo al puerto 8000** 

Te pedirá uno nombre arbritario para el servicio, por ejemplo http-picam8000

Dejar pasar un tiempo para que todo quede registrado

##8.6.3 Entrar a WebIOPi desde Internet

Entramos en [remote.it](http://remote.it) nos logueamos y entramos en el servicio, ASI DE FACIL automáticamente saltará a la página

![](/assets/webpiop-remoteit.jpg)

OJO nos pedirá un usuario y contraseña, no es la de la Raspberry, sino la del servicio Wepiopi que si te acuerdas [cuando lo vimos](/8-camara/82-webiopi.md), por defecto era webiopi y contraseña raspberry

![](/assets/webiopi-remoteit2.jpg)

##8.6.4 Instalar el servicio para MJPG-Streamer

Es exáctamente igual que 8.6.2 pero en vez del puerto 8000 ponemos 8080 y ponemos un nombre arbritario, por ejemplo http-picam8080

Y si te lo preguntas: **Sí**, podemos tener los dos a la vez instalados

##8.6.5 Entar en MJPG-Streamer desde Internet

Aquí hay que hacer un paso previo ARRANCAR EL SERVICIO MJPG-Streamer

Para ello entramos SSH de forma remota, [eso ya lo has visto aquí](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet/113-ssh-y-vnc-desde-internet.html)

Y por comandos entramos en la carpeta donde tenemos instalado mjpg-stramer y tecleamos 

>./start.sh

![](/assets/start-sh.jpg)

UNA VEZ ARRANCADO **NO QUITAMOS LA VENTANA** dejamos el servicio corriendo

Entramos en [remote.it](http://remote.it) nos logueamos y entramos en el servicio pero ahora el que has creado tipo http con puerto 8080, ASI DE FACIL automáticamente saltará a la página exáctamente igual que en [8.5 Ver la cámara](/8-camara/84-ver-la-camara.md) pero en vez de por red local, desde cualquier parte del mundo !

![](/assets/mjpg-stramer-remoteit.jpg)


