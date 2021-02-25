# ROBER MARCIANO ¿Por qué la elección del robot comercial ALPHABOT?

Para hacer el rover marciano tenemos unas características que cumplir y resolver con ¿Arduino? ¿Raspberry? ¿Qué lenguaje? ...

* Control a distancia desde **Internet**:
  * Con **Arduino** resulta complejo tener un control del dispositivo via remoto, es fácil via Bluetooth pero se busca un control totalmente remoto.
  * Con **Raspberry** es mucho más sencillo, el sistema operativo por excelencia es Linux y es un SO pensado para controlar remotamente.
* Una **vídeocámara** esencial para ver el paisaje marciano que queremos ver:
  * Con Arduino es muy dificil
  * Con Raspberry es muy fácil, está preparado para ello y hay software libre que nos da soporte.
* **Motores, sensores, brazo robótico ...**
  * Con Arduino es fácil
  * Con Raspberry tiene:
      * Desventajas, necesitas electrónica entre las GPIO y los sensores o motores, es decir no permite conexiones directas con la Raspberry [como ya has visto](https://catedu.github.io/raspberry-muy-basico/2-gpio.html), luego necesitamos de un kit comercial que nos falicile las cosas.
      * Ventajas pues programamos en la misma Raspbery [como ya has visto](https://catedu.github.io/raspberry-muy-basico/6-vnc.html)

Si pones las palabras **_Raspberry_** y _**Robot**_ en cualquier buscador verás que hay muchas opciones y kits comerciales, elegimos el kit Alphabot para hacer nuestro rover marciando, pues veremos en [VENTAJAS](/ventajas.md) que sirve tanto para Raspberry y Arduino y tiene una buena dotación de sensores, en contra tiene importantes defectos de diseño, esto lo veremos en [DESVENTAJAS](/desventajas.md) pero con el precio que tiene, no se puede pedir más.

####¿Qué incluye este robot?

* **Raspberry PI3+** con la opción de añadir un Arduino. Puede ir con uno de los dos o ambos. En este curso sólo trabaremos con la Raspberry.
* **Dos motores** con el L298P driver ¿Qué es eso? Pues parecido al L293 [míralo aquí](https://catedu.github.io/programa-arduino-mediante-codigo/montaje_con_circuito_l293.html). Proporciona 2A a los motores y tienen diodo de protección para manejarlos con seguridad.
* **Dos sensores de IR de proximidad** no tienen tanta precisión como los sensores de ultrasonidos, pero hacen su función para evitar obstáculos. Hay posibilidad de añadir un sensor de Ultrasonidos (no incorporado pero lo veremos [aquí](/45-posibilidad-ultrasonidos.md))
* **Sensores de paso** en los motores por lo tanto control de velocidad y de recorrido.
* **Control remoto por IR** con su mando, lo que aumenta nuestra posibilidad creativa.
* **Módulo con 5 sensores sigue-líneas** con un TLC1543 conversor Analógico Digital que lo veremos detenidamente.
* **Brazo robótico** con dos servos que permiten trabajar didácticamente con este importante elemento.
* **Cámara web** que añade una importante gamificación al kit, y al trabajar con la Raspberry en vez de con el Arduino, su control vía web es fácil, podemos ver nuestro paisaje marciano si tenemos conexión con el robot.

![](/assets/apphabot1.png)
Fondo: Paisaje de Marte tomado por el Curiosity © NASA
