---
layout: post
title:  "Motor Paso a Paso Lineal: Diseño e Implementación"
date:   2016-04-22 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sc01.jpg"><img align="left" src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sc01-580x487.jpg" alt="sc01" width="300" /></a>

El <a href="https://es.wikipedia.org/wiki/Motor_paso_a_paso">Motor Paso a Paso</a> es un tipo de motor que utiliza la alternancia de excitación en una serie de bobinas dispuestas en fases para realizar un movimiento gradual y controlado. El motor PaP más conocido es el radial que emplea esta alternancia de fase para generar un movimiento circular.

Lo que hoy traigo es el diseño y la implementación que he realizado de un tipo de motor Paso a Paso un tanto peculiar: el motor PaP lineal. Este tipo de motor, conservando el mismo concepto de la alternancia de excitación de bobinas, puede generar un tipo de movimiento lineal a pasos discretos de una determinada longitud. Discutiremos en esta entrada los conceptos generales de los motores Paso a Paso y el diseño e implementación concreta de este motor lineal.

<!--more-->

Como de costumbre, antes de comenzar con los conceptos de base, una pequeña presentación del motor que terminaremos construyendo al final de la entrada:

<div style="text-align: center">
<video width="640" controls>
  <source src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/LinearStepperVideo.webm" type="video/webm">
</video>
</div>

El motor en cuestión, visto desde Autodesk Inventor tiene esta pinta:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB01.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB01-580x346.png" alt="DesignB01" width="580" height="346" /></a></div>

Antes de profundizar en el diseño concreto de este motor lineal vamos a asentar los conceptos básicos de este tipo de motores. He desempolvado el 3d Studio Max y he hecho algunos gráficos que espero que hagan un poco más comprensible la siguiente sección.

## Conceptos generales
Para poder entender cómo funciona un motor Paso a Paso lineal primero debemos entender el funcionamiento de un motor Paso a Paso radial convencional. Para hacer ese ejercicio partiremos del siguiente motor:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper01.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper01-580x435.png" alt="sampleStepper01" width="580" height="435" /></a></div>

&nbsp;

El motor que aparece en la ilustración está compuesto por un núcleo magnético permanente que actúa a modo de rotor y un estátor formado por un armazón metálico y cuatro bobinas de cobre. Las bobinas están dispuestas en dos fases, anotadas como A y B, lo que convierte a este motor en un motor paso a paso <strong>bipolar. </strong>

Cada fase está bobinada de forma simétrica a ambos lados del estátor, es decir, si miramos la fase A desde el eje central del armazón nos la encontraremos bobinada de forma horaria en un extremo y de forma antihoraria en el otro. Esto provocará que el campo magnético generado cuando excitemos cada una de las fases genere polos opuestos a cada lado del estátor.

Al excitar cada fase del motor obligaremos al rotor a posicionarse en un único ángulo estable y con una secuencia ordenada de excitaciones para cada fase lograremos que el motor rote en el sentido que queramos. Una posible secuencia de excitación, que es la que utilizaremos en el resto de la entrada, es la siguiente:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/CoilSequence.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/CoilSequence-580x429.png" alt="CoilSequence" width="450" height="333" /></a></div>

&nbsp;

Como se observa utilizamos las cuatro combinaciones disponibles para un motor bipolar: la fase A con excitación directa, la fase B con excitación directa y nuevamente ambas fases con excitación inversa. Siguiendo esta secuencia de excitación de las fases el motor pasaría por los siguientes estados:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper02.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper02-580x435.png" alt="sampleStepper02" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper03.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper03-580x435.png" alt="sampleStepper03" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper04.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper04-580x435.png" alt="sampleStepper04" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper05.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleStepper05-580x435.png" alt="sampleStepper05" width="450" /></a></div>

Comprendido el funcionamiento básico de un motor Paso a Paso radial podemos comenzar a analizar el motor Paso a Paso lineal. En realidad un motor Paso a Paso lineal es un caso específico de un motor radial con un <strong>radio infinito</strong>. En este motor de radio infinito las bobinas quedarían dispuestas en linea. Supongamos la siguiente disposición de bobinas:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper01.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper01-580x435.png" alt="sampleLinearStepper01" width="580" height="435" /></a></div>

&nbsp;

Analizando el gráfico anterior vemos elementos familiares similares a los del motor radial que hemos visto anteriormente. En primer lugar apreciamos las dos fases A y B, esta vez materializadas en ocho bobinas (cuatro cada una). Si analizamos cada una de las fases por separado encontramos que la primera bobina está dispuesta de forma horaria, la segunda de forma antihoraria, la tercera de forma horaria y la cuarta de forma antihoraria. De esta forma cuando excitemos una de las fases se generarán polos opuestos en las bobinas contiguas atrayendo al núcleo que, en este caso, está diseñado para encajar a la distancia de dos bobinas contiguas dentro de cada fase (Cada tres bobinas en general).

Si excitamos las bobinas con la secuencia que hemos visto anteriormente este peculiar motor pasará por los estados que ilustro a continuación:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper02.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper02-580x435.png" alt="sampleLinearStepper02" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper03.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper03-580x435.png" alt="sampleLinearStepper03" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper04.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper04-580x435.png" alt="sampleLinearStepper04" width="450" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper05.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/sampleLinearStepper05-580x435.png" alt="sampleLinearStepper05" width="450" /></a></div>

&nbsp;

Como se observa en las ilustraciones se produce un movimiento lineal al seguir la misma secuencia de excitación que utilizamos con el motor radial. Este es el concepto de base que he utilizado para diseñar un motor Paso a Paso lineal muy sencillo ya que las implementaciones comerciales, tanto de motores radiales como de motores lineales, están basadas en conceptos ligeramente distintos.

Para asentar los conceptos base tanto de los motores radiales como de los lineales y tratar de ilustrar de forma gráfica el diseño que trataremos en la siguiente sección he hecho una animación (Muy al estilo <em>How Its Made, </em>sin voz en off lamentablemente) que espero que sirva para comprender mejor el funcionamiento de este tipo de motores.

<div style="text-align: center">
<video width="640" controls>
  <source src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/anim.webm" type="video/webm">
</video>
</div>


## Construyendo un PaP lineal
Si el lector permanece aún sentado, sobrecogido por los impresionantes efectos especiales de la animación anterior, podemos proceder con el diseño de nuestro motor PaP lineal. Como de costumbre comenzamos con algunas capturas del modelo en Autodesk Inventor:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB011.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB011-580x346.png" alt="DesignB01" width="450" /></a><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB02.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB02-580x346.png" alt="DesignB02" width="450" /></a><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB03.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/DesignB03-580x345.png" alt="DesignB03" width="450" /></a></div>

Tanto el armazón donde quedarán alojadas las bobinas como el núcleo móvil estarán impresos en plástico ABS. Las bobinas tienen un grosor máximo de 5.5 milímetros y las bobinaremos con hilo de cobre esmaltado de 0.2 milímetros de diámetro. El núcleo de las bobinas estará formado por tornillos de 2.5 milímetros de diámetro y 20 milímetros de longitud.

Para el núcleo móvil utilizaremos imanes de magnetización axial de 2.5 milímetros de diámetro y 5 milímetros de longitud. Los huecos de la pieza móvil están diseñados para que los imanes encajen sin necesidad de utilizar ningún adhesivo. Utilizaremos un total de 32 imanes, lo que resulta en una libertad de movimiento de 60 milímetros.

El desplazamiento por cada paso que realice el motor será de tres milímetros como puede apreciarse en la guía milimetrada que se muestra en el vídeo al comienzo de esta entrada. Esta distancia es la distancia a la que se encuentran separadas las bobinas de las diferentes fases y, por tanto, la distancia mínima de paso del motor.

A continuación como siempre los ficheros STL que he utilizado para imprimir las piezas:
<table>
<tbody>
<tr>
<td><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/LongShaft.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/LongShaft-580x355.png" alt="LongShaft" width="200" height="122" /></a></td>
<td><a href="http://j0k3n.com/src/linearstepper/ChassisLowContact.stl">ChassisLowContact.stl</a></td>
</tr>
<tr>
<td><a href="http://j0k3n.com/src/linearstepper/LongShaft.stl"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/chassisLowContact.png" alt="chassisLowContact" width="200" /></a></td>
<td><a href="http://j0k3n.com/src/linearstepper/LongShaft.stl">LongShaft.stl</a></td>
</tr>
</tbody>
</table>
Una vez impresas las piezas el primer paso es bobinar las dos fases. Recordemos que las cuatro bobinas de cada fase deben estar bobinadas alternando el sentido horario y antihorario. He utilizado una broca de 2.5 milímetros y grasa de litio para facilitar la extracción de cada bobina una vez bobinada.

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build01.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build01-580x326.jpg" alt="build01" width="580" height="326" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build02.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build02-580x326.jpg" alt="build02" width="580" height="326" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build03.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build03-580x326.jpg" alt="build03" width="580" height="326" /></a></div>

&nbsp;

Una vez colocadas las bobinas en el armazón de plástico el aspecto del motor es el siguiente:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build04.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build04-580x326.jpg" alt="build04" width="580" height="326" /></a> <a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build05.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build05-580x326.jpg" alt="build05" width="580" height="326" /></a></div>

&nbsp;

## Control del motor: Drivers PaP
Lo bueno del diseño es que sigue la misma teoría que un motor Paso a Paso radial. Esto implica que para hacerlo funcionar podemos utilizar cualquier configuración electrónica que sirva para hacer funcionar un motor Paso a Paso bipolar.

El montaje que he realizado utiliza el <em>driver</em> de potencia L298 y la placa Arduino Mega. Podemos utilizar la librería <i>Stepper</i> de Arduino para controlar el movimiento del motor sin problema. El esquemático de este montaje es el siguiente:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/elect.png"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/elect-580x305.png" alt="elect" width="580" height="305" /></a></div>

Dejo aquí una imagen de la implementación en la placa de prototipos:

<div style="text-align: center"><a href="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build06.jpg"><img  src="/assets/2016-04-22-motor-paso-a-paso-lineal-diseno-e-implementacion/build06-580x326.jpg" alt="build06" width="580" height="326" /></a></div>

Como se puede observar estoy utilizando una salida PWM de Arduino para controlar la potencia del motor ya que lo estoy alimentando con una fuente de sobremesa a 12 voltios y quiero regular la corriente que circula a través de las bobinas.

##  Conclusión
Con no muchas horas de diseño es fácil conseguir una versión funcional de un motor paso a paso lineal con los beneficios de que, al estar basado en un motor paso a paso bipolar radial, podemos utilizarlo con cualquier <em>driver</em> que funcione con este tipo de motores. Los motores Paso a Paso lineales que se utilizan en industria se basan en conceptos ligeramente distintos para producir el movimiento pero queda fuera del ámbito de esta entrada. El objetivo era implementar una versión simplificada de un motor Paso a Paso lineal para ilustrar su semejanza a un motor radial.

Me sorprende que, a pesar de no haber dedicado mucho tiempo a diseñar este motor, se consigue una precisión relativamente buena para un prototipo. Si nos fijamos en las pruebas que se muestran en el video al comienzo de esta entrada podemos observar que, aún incrementando la velocidad del motor (El movimiento más rápido lo realizo a un paso cada 15 milisegundos), el motor no pierde pasos al retornar a la posición original.

Ha sido muy divertido diseñar y ver funcionar este motor, espero que haya sido de interés y volveré pronto con nuevos inventos.
