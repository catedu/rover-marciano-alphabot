# Configuración

1. INSTALAR SISTEMA OPERATIVO Tienes que instalar el sistema operativo Raspbian en la micro tarjeta SD (que ya tiene **Python**) para ello tienes que seguir los pasos de los apuntes de [**los apuntes Raspberry muy básico**](https://catedu.github.io/raspberry-muy-basico/). Concrétamente el [capítulo 3](https://catedu.github.io/raspberry-muy-basico/3-raspbian.html) si quieres manejar este robot **via red local**. Pero si además quieres controlar este robot remotamente **por Internet**, entonces te recomendamos intalar la imagen de Raspbian con los scripts de remote.it para poderlo manejar remotamente. [Ver Capítulo 11-2 opción A](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet/112-instalar-remoteit-en-la-raspberry.html)
1. CONECTARLO VIA WIFI Una vez instalado tienes que conectar la Raspberry a la wifi, para ello sigue los pasos marcados en el [capítulo 4](https://catedu.github.io/raspberry-muy-basico/4-primera-comunicacion.html).
1. OPCIONAL : COMUNICACIÓN VIA TEXTUAL Es interesante y útil [comunicarte con la Raspberry via texto por SSH](https://catedu.github.io/raspberry-muy-basico/5-ssh.html), [cambiar el usuario, contraseña](https://catedu.github.io/raspberry-muy-basico/6-cambiar-usuario-y-contrasena.html), y [aprender a apagar por comando](https://catedu.github.io/raspberry-muy-basico/7-apagar.html).
1. OBLIGATORIO COMUNICACIÓN VIA GRÁFICA Es el método que se usará en este curso, por VNC lo tienes explicado en [el capítulo 8](https://catedu.github.io/raspberry-muy-basico/8-vnc.html).

## ¿Cómo ejecuto un programa?

Vía [VNC de forma gráfica](https://catedu.github.io/raspberry-muy-basico/8-vnc.html), creas un fichero con extensión .py le das dos cliks y ya está !! Se abre el editor de Python para que escribas tus programas. (pues Raspbian tiene Python de forma nativa). Se ejecuta con el botón Play (redondo verde de la figura) y se para con el rojo. Esta será la forma de trabajar en este curso. **OJO ESTAMOS HABLANDO DEL ESCRITORIO DE LA RASPBERRY** que desde tu ordenador lo estas viendo por VNC.

![](/assets/play)

>Nota: También se puede hacer de forma textual con el [protocolo SSH](https://catedu.github.io/raspberry-muy-basico/5-ssh.html) ejecutando la orden  python.
>Por ejemplo: Tenemos un programa llamado miprograma.py en la carpeta Aphpabot de la Raspberry luego las instrucciones serían en el terminal ssh:
>cd ~/AlphaBot/  
>sudo python miprograma.py

## Desde Internet

El curso se puede hacer perfectamente desde **LA RED LOCAL** accediendo a la Raspberry por una IP fija tal y como hemos explicado en los enlaces del principio de esta misma página.

Pero es educativo aprender a usar este rover totalmente a distancia desde Internet, simplemente sustituyendo la IP de la Raspberry por la dirección que nos proporciona Remote.it [siguiendo estos pasos](https://catedu.github.io/raspberry-muy-basico/11-conectando-desde-internet.html) por lo tanto es recomendable descargar ya el sistema operativo con los comandos de Remote.it ya preinstalados.

O sea: ¿Puedo manejar mi Alphabot en Marte si ponen Internet? Si. No es ciencia ficción, hay un plan para [poner Internet en la luna en 2024](https://retina.elpais.com/retina/2020/10/20/innovacion/1603209140_262809.html).

![](/assets/curiosity2.jpg)

[De NASA/JPL/Cornell University, Maas Digital LLC](http://photojournal.jpl.nasa.gov/catalog/PIA04413), [Dominio público](https://commons.wikimedia.org/w/index.php?curid=565283)
