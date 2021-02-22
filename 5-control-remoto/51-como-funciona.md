#Protolo NEC
Alphabot tiene un receptor LFN0038K compatible con el protocolo estandard NEC y el mando emisor que acompaña a este kit también es compatible con él. Encima, para complicarnos más las cosas, tiene configuración PULL-UP como el resto de sensores de este robot, por lo que si recibe del mando a distancia un 1 lógico, él transmite un 0 y viceversa.

 Una señal con el protocolo NEC es una especie de señal PWM donde un '0' es es un ciclo de 1.125ms la emisión de una señal de 0.565ms y un '1' lógico o mismo pero en un intervalo de 2.25ms, se ve mejor con un dibujo:
 
 ![](/assets/necprotocolo.jpg)
 
 El protocolo establece que primero se emite 9ms de una señal alta, y luego 4.5ms de señal baja para empezar el envío de una señal de 8 bits, empezando por el bit más bajo LSB hasta el más alto MSB y luego su complemento. Todo en una señal de 38kHz donde se modula primero la dirección y luego el comando. Mejor con un dibujo ¿no?
 
 ![](/assets/necprotocolo2.jpg)
 
 Cada comando se envía una sola vez al menos que mantengas el botón pulsado más de 110ms. El formato de duplicación es según este dibujo:
 
 ![](/assets/necprotocolo3.png)