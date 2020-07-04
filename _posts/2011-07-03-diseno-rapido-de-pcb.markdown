---
layout: post
title:  "Diseño rápido de PCB"
date:   2011-07-03 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<span>Sin duda el diseño de PCB es uno de los pequeños artes modernos para los que nos dedicamos, sea de la forma que sea, a la electrónica. Sin embargo, en ocasiones este diseño implica técnicas fuera de nuestro alcance o <span>sencillamente</span> demasiado costosas para la envergadura de nuestro proyecto. Es por esto que planteo en este entrada un método sencillo para el diseño de PCB con muy pocos recursos.</span>

<span><!--more-->
</span>

<span>En ocasiones, el <span>prototipado</span> rápido requiere grabar nuestros circuitos de manera permanente en una PCB ya que las <span>protoboard</span> se nos quedan cortas y las placas <span>preperforadas</span>, poco elegantes. El problema es que muchos de los métodos para diseñar PCB no siempre quedan a nuestro alcance. Concretamente, los dos métodos más frecuentes, el revelado por insolación y la transferencia de <span>toner</span>, requieren de materiales de los cuales no siempre disponemos.</span>

<span>El método que planteo en esta entrada requiere de materiales que podemos encontrar en nuestra tienda de electrónica y otros muy sencillos de adquirir. Para este <span>tutorial</span> <span>necesitaremos</span> una placa de cobre, un atacador rápido a base de ácido clorhídrico y perborato sódico fácil de adquirir en cualquier tienda de electrónica, un rotulador <span>edding</span> permanente (En mi caso un <span>edding</span> 3000) y una broca para taladrar PCB de 1mm, también <span>facil</span> de obtener en cualquier tienda de electrónica o ferretería.</span>

<span>Para ilustrar este método vamos a realizar el circuito que vemos en la imagen a continuación. Es una sencilla fuente de <span>alimentación</span> simétrica de 15V.</span>

<div style="text-align: center"><a href="/assets/legacy/circuito.png"><img  title="circuito" src="/assets/legacy/circuito.png" alt="" width="490" height="253" /></a></div><span>El diseño sobre la PCB, obtenido con ARES de <span>Proteus</span> es el siguiente. Vemos a la izquierda la PCB desde arriba y el espejo (Para copiarlo en la placa) a la derecha.</span>
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/pcb1.png"><img  title="pcb1" src="/assets/legacy/pcb1-300x150.png" alt="" width="300" height="150" /></a></td>
<td><a href="/assets/legacy/pcb2.png"><img  title="pcb2" src="/assets/legacy/pcb2-300x150.png" alt="" width="300" height="150" /></a></td>
</tr>
</tbody>
</table>
<span><span>Comenzaremos</span> cortando nuestra placa de cobre a la medida deseada, en nuestro caso 100x50mm y más adelante puliremos el cobre bien con una lija fina, bien con un cepillo de latón. Vemos a continuación dos imágenes de este proceso.</span>
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/P7030269.jpg"><img  title="P7030269" src="/assets/legacy/P7030269-300x213.jpg" alt="" width="300" height="220" /></a></td>
<td><a href="/assets/legacy/P7030274.jpg"><img  title="P7030274" src="/assets/legacy/P7030274-300x220.jpg" alt="" width="300" height="220" /></a></td>
</tr>
</tbody>
</table>
Cuando hayamos pulido la superficie del cobre la placa quedará con un aspecto brillante como vemos en la siguiente imagen:

<div style="text-align: center"><a href="/assets/legacy/P7030276.jpg"><img  title="P7030276" src="/assets/legacy/P7030276-300x226.jpg" alt="" width="300" height="226" /></a></div><span>Este paso es fundamental para que el revelado se haga correctamente. El siguiente paso será dibujar las pistas sobre la placa. <span>Efectivamente</span> este paso determinará el acabado de la placa mientras que en otros métodos el acabado es de resolución digital. En cualquier caso, mi objetivo es el diseño de PCB para el <span>prototipado</span> rápido, no para acabados industriales luego es un <span>procedimiento</span> más que factible. Aún así el acabado, como siempre digo en caso de trabajos manuales, dependerá de la pericia del lector.</span>

<span>Lo ideal es ayudarse de una regla y prestar mucha atención a las distancias entre las patas de los componentes con distancias fijas como los circuitos integrados, <span>clemas</span> y otros. Vemos un par de <span>imágenes</span> de este proceso a continuación:</span>
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/P70302781.jpg"><img  title="P7030278" src="/assets/legacy/P70302781-300x225.jpg" alt="" width="300" height="225" /></a></td>
<td><a href="/assets/legacy/P7030287.jpg"><img  title="P7030287" src="/assets/legacy/P7030287-300x209.jpg" alt="" width="300" height="225" /></a></td>
</tr>
</tbody>
</table>
<span>Como podemos <span>obervar</span> hemos copiado las pistas que aparecían en el esquemático de más arriba (con alguna <span>simplificación</span>). Si ocurriera que alguna de las pistas, por error, se conecta con otra al dibujarla podemos <span>rectificarlo</span> limando el error con un <span>cutter</span> o cualquier otra herramienta.</span>

El siguiente paso es revelar la placa con atacador rápido. Existen algunos atacadores de fabricación casera a base de Aguafuerte y agua oxigenada pero, por experiencia personal, puedo decir que no tienen buenos resultados. Nuestro atacador está formado por dos recipientes, separados, de ácido clorhídrico y perborato sódico que habremos de mezclar a partes iguales en un recipiente de vidrio o plástico.

<span>En esta solución <span>sumergiremos</span>, con la cara de las pistas dibujadas hacia abajo, nuestra PCB y la dejaremos <span>ahi</span> durante unos 4 o 5 minutos. El ácido comenzará a disolver el cobre que no ha sido protegido con el rotulador y quedarán tan sólo las pistas marcadas con este. Se ha de prestar especial atención al tiempo que pasa la placa sumergida ya que un exceso de exposición al ácido podría provocar que algunas de las pistas tapadas con el rotulador se disolviesen y habría que estañarlas después.</span>

Podemos mirar de vez en cuando, girando la placa, como evoluciona el proceso como vemos en las imágenes a continuación.
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/P7030289.jpg"><img  title="P7030289" src="/assets/legacy/P7030289-300x225.jpg" alt="" width="300" height="225" /></a></td>
<td><a href="/assets/legacy/P7030292.jpg"><img  title="P7030292" src="/assets/legacy/P7030292-300x225.jpg" alt="" width="300" height="225" /></a></td>
</tr>
<tr>
<td><a href="/assets/legacy/P7030295.jpg"><img  title="P7030295" src="/assets/legacy/P7030295-300x225.jpg" alt="" width="300" height="225" /></a></td>
<td><a href="/assets/legacy/P7030298.jpg"><img  title="P7030298" src="/assets/legacy/P7030298-300x225.jpg" alt="" width="300" height="225" /></a></td>
</tr>
</tbody>
</table>
El resultado final es nuestra placa con las pistas marcadas con el rotulador permanente que tendremos que borrar. La acetona puede servir para limpiar las pistas aunque también podemos volver a lijar la placa con cuidado para no romper ninguna de las pistas.

Si alguna de las pistas se hubiese cortado por una exposición excesiva al ácido podríamos estañarla utilizando un soldador para unir los dos extremos de la pista separada. La placa resultante la vemos a continuación:
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/P70302991.jpg"><img  title="P7030299" src="/assets/legacy/P70302991-300x213.jpg" alt="" width="300" height="213" /></a></td>
<td><a href="/assets/legacy/P7030300.jpg"><img  title="P7030300" src="/assets/legacy/P7030300-300x186.jpg" alt="" width="300" height="213" /></a></td>
</tr>
</tbody>
</table>
El siguiente paso que tendremos que realizar es el de perforación de la placa. Para ello, como dijimos anteriormente, utilizaremos una broca de 1mm para todos los componentes aunque se pueden utilizar brocas más finas para algunos de ellos.

Tras perforar todos los agujeros procederemos a soldar todos los componentes en sus respectivos lugares. Vemos algunas imágenes de este proceso a continuación:
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/P7030302.jpg"><img  title="P7030302" src="/assets/legacy/P7030302-300x225.jpg" alt="" width="300" height="225" /></a></td>
<td><a href="/assets/legacy/P7030306.jpg"><img  title="P7030306" src="/assets/legacy/P7030306-300x225.jpg" alt="" width="300" height="225" /></a></td>
</tr>
<tr>
<td><a href="/assets/legacy/P7030308.jpg"><img  title="P7030308" src="/assets/legacy/P7030308-300x225.jpg" alt="" width="300" height="225" /></a></td>
<td><a href="/assets/legacy/P7030310.jpg"><img  title="P7030310" src="/assets/legacy/P7030310-300x205.jpg" alt="" width="300" height="225" /></a></td>
</tr>
</tbody>
</table>
<span>Nuestra PCB está lista para funcionar en pocos pasos que requieren de muy pocos materiales. El último paso es probar el <span>funcionamiento</span> y comprobar que es el deseado en cuyo caso habrá finalizado nuestro trabajo.</span>

<div style="text-align: center"><a href="/assets/legacy/P7030311.jpg"><img  title="P7030311" src="/assets/legacy/P7030311-300x225.jpg" alt="" width="300" height="225" /></a><a href="/assets/legacy/20110703-0002.png"><img  title="20110703-0002" src="/assets/legacy/20110703-0002-300x225.png" alt="" width="300" height="225" /></a></div>Podemos observar que el funcionamiento de la fuente es correcto ya que proporciona 15V y -15V medidos desde la tierra con el osciloscopio. Una nota adicional para el lector: <em>Cuando pruebe su PCB no lo haga con todas las puntas de la soldadura, en la cara inferior de la PCB, tocando con una placa de metal conductor.... Si mira dos imágenes más atrás entenderá de que hablo...</em>

<span>Humaredas aparte, nuestro proceso de <span>construcción</span> de PCB ha concluido. Los materiales que hemos utilizado han sido los más sencillos de conseguir en nuestra tienda de electrónica y también los más baratos de modo que el lector no tiene ya excusa para no pasar sus diseños en las poco elegantes placas <span>preperforadas</span> a una muy elegante PCB. </span><em>
</em>