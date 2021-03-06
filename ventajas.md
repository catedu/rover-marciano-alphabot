# Ventajas

## Ventaja 1: Raspberry, Arduino o ambos
Lo primero que nos gustó es su versatilidad de que sirve tanto para **ARDUINO**, como para la **RASPBERRY**.
Tiene un regulador LM2596 que proporciona una tensión estable de 5V para las dos placas.
En la figura puedes ver que simplemente cambiando los jumpers amarillos de lugar decides quien actúa el Arduino o la Rasbperry, incluso los dos a la vez !! puedes hacer que los motores vayan con Arduino y los sensores con Raspberry.

Incluso deja en la parte superior los conectores del Arduino con la posibilidad de poner una Shield.

![](/assets/2018-06-27 20_37_59-PhotoFiltre.jpg)
![](/assets/both.png)

### Opción Arduino

Para trabajar con el Arduino tiene en la parte trasera dos conectores exclusivos:

![](/assets/uart.jpg)

* 11=Conexión por **UART** (comunicación universal transmisor/receptor, asíncrono ) para poner un módulo Bluetooth por ejemplo un JY-MCU HC-06 [igual que en el curso Arduino de Aularagón aquí](https://catedu.github.io/programa-arduino-mediante-codigo/mdulo_bluetooth.html) esto posibilita utilizar Alphabot con el móvil o incluso con la [voz](https://catedu.github.io/programa-arduino-mediante-codigo/6235-m8-coche-con-voz.html)

![](/assets/uart3.jpg)

* 12=Una interface SPI para conectar un módulo wifi NRF24L01, no obstante recomendamos para usar wifi usar Raspberry

### Opción Arduino+ RASPBERRY

Tiene **un interruptor UART SWITCH** que permite establecer una comunicación serie entre Raspberry y Arduino, conectando D1 del Arduino con P TX de Raspberry y D0 del Arduino con P RX de Rasperry.

![](/assets/uart2.jpg)

### Opción sólo Raspberry

**En este curso SÓLO VAMOS A TRABAJAR CON LA RASPBERRY** por lo tanto no trabajaremos con el conector UART pues la Raspberry ya tiene Bluetooth y Wifi integrados.

## Ventaja 2: Buena relación prestaciones/precio (no calidad/precio)
Nosotros no somos comerciales, ni intermediarios, sólo somos formadores. Cuesta aproximadamente unos 100€ se puede conseguir en: (ojo, que hay modelos **sin** Raspberry o **con** Raspberry)

* [Aliexpres](https://es.aliexpress.com/wholesale?catId=0&initiative_id=SB_20180627103432&SearchText=alphabot)
* En la web del fabricante [Waveshare](https://www.waveshare.com/product/robotics/mobile-robots/raspberry-pi-robots.htm)

![](/assets/waveshare.png)

## Ventaja 3 Pilas 18650

No son las "normales AA o AAA" pero proporcionan 3.7V y más de 1.000mAh cada una lo que asegura la alimentación del robot+raspberry de forma autónoma, esto es importante si lo vamos a dejar en marte :

![](/assets/marte1.jpg)

Fuente: Fotomontaje del original [NASA.gov](https://www.nasa.gov/image-feature/jpl/perseverance-touches-down-on-mars)
