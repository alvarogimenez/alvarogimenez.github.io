---
layout: post
title:  "Cómo construir una etapa de 10W"
date:   2011-08-03 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_front2.jpg"><img align="left" title="etapa_front2" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_front2-300x224.jpg" alt="" width="300" height="224" /></a>Hace un tiempo llegaron a casa un par de altavoces buenos y decidí, dado que no tenía nada con que alimentarlos, construir una etapa de potencia. La etapa que he construido y cuyo proceso y esquemáticos os dejo en esta entrada es una etapa de 10W de clase AB que utiliza el integrado TDA2030.

El resto de componentes son fáciles de adquirir y a un precio asequible. La interfaz de la etapa será sencilla, como se puede ver en la imagen de la izquierda y, después de varias pruebas, los resultados son más que satisfactorios.

He dividido este proyecto en tres partes: la etapa de potencia, la fuente de alimentación y un vúmetro digital que diseñé y que aún no he incorporado a la carcasa de la fuente pero que es plenamente funcional. Además de estos elementos he decidido añadir un ventilador pequeño pero potente para refrigerar el interior de la caja de montaje dado que este amplificador se calienta bastante despues de un rato de uso.

<!--more-->Etapa de potencia

Como dije antes he optado por el integrado TDA2030, previsto para ser usado como amplificador de clase AB y cuyas especificaciones podeis encontrar <a href="http://www.st.com/stonline/books/pdf/docs/1458.pdf">aqui</a>.

He modificado el esquemático para fuente simétrica reduciendo la ganancia. El circuito es el siguiente:
<p style="text-align: left;"><div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_etapa1.jpg"><img  title="esquematico_etapa" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_etapa1.jpg" alt="" width="550" height="501" /></a></div>
Dado que estamos construyendo una etapa estéreo tendremos que duplicar dicho circuito para amplificar ambas entradas.</p>
<p style="text-align: left;">He tenido que jugar un poco con el espacio ya que tenía que meter todos los circuitos en una cjaa de 150x150mm. El circuito resultante de la etapa lo he separado de la fuente de alimentación y sus dimensiones finales son de 100x100mm. Vemos el esquema a continuación:</p>

<table align="center">
<tbody>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_schematic.png"><img  title="etapa10W_schematic" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_schematic-300x300.png" alt="" width="300" height="300" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_schematic_mono.png"><img  title="etapa10W_schematic_mono" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_schematic_mono-300x300.png" alt="" width="300" height="300" /></a></td>
</tr>
<tr>
<td colspan="2"><div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_3dview.png"><img  title="etapa10W_3dview" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa10W_3dview.png" alt="" width="607" height="439" /></a></div></td>
</tr>
</tbody>
</table>
En este circuito he añadido también un regulador de voltaje a 12 voltios para alimentar un ventilador de 40x40mm dado que la etapa se calentará bastante cuando esté en funcionamiento. Este circuito es el siguiente:
<div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_ventilador.jpg"><img  title="esquematico_ventilador" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_ventilador.jpg" alt="" width="500" height="191" /></a></div>No pude sacar imágen de la placa sin montar en la caja pero os dejo una foto de como queda la placa dentro de la caja en el montaje final. He puesto dos disipadores de TO3 a los integrados dado que los disipadores pequeños para TO220 se calientan mucho y los más grandes para este mismo encapsulado hacian el diseño demasiado grande.
<h2 style="text-align: left;"><div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_circuito.jpg"><img  title="etapa_circuito" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_circuito.jpg" alt="" width="512" height="371" /></a></div>Fuente de alimentación</h2>
La etapa, tal y como la hemos diseñado, requiere de una fuente de alimentación simétrica de 15 V. Utilizaré el esquemático que ya he utilizado en alguna de mis entradas anteriores:

<div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_fuente.jpg"><img  title="esquematico_fuente" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_fuente.jpg" alt="" width="600" height="294" /></a></div>De nuevo, dado que tengo poco espacio en la caja para el montaje final, he tenido que reducir bastante el tamaño de la fuente. Al final he conseguido un circuito de tan solo 45x45mm como vemos a continuación:
<table align="center">
<tbody>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/fuente_schematic.png"><img  title="fuente_schematic" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/fuente_schematic-300x300.png" alt="" width="300" height="300" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/fuente_schematic_mono.png"><img  title="fuente_schematic_mono" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/fuente_schematic_mono-300x300.png" alt="" width="300" height="300" /></a></td>
</tr>
<tr>
<td colspan="2&gt; &lt;a href="><img  title="fuente_3dview" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/fuente_3dview.png" alt="" width="530" height="403" /></td>
</tr>
</tbody>
</table>
De nuevo no he tomado fotografías de la placa aislada pero sí tengo alguna imagen de la fuente una vez realizado el montaje final:
<p style="text-align: left;"><div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_circuito2.jpg"><img  title="etapa_circuito2" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_circuito2.jpg" alt="" width="512" height="408" /></a></div>El transformador que estoy utilizando es un transformador de 500mA simétrico de 18 V y aún asi, como veis, ocupa bastante espacio en el montaje.</p>

<h2 style="text-align: left;">Vúmetro digital</h2>
Aunque no he tenido tiempo de añadirlo aún al montaje final se puede observar que entre las salidas del circuito principal de la etapa hay una destinada al vúmetro. Para realizar este indicador de volumen he utilizado el integrado LM3914  (Se podría utilizar el 15 de la misma forma sólo que la salida sería logarítmica en vez de lineal).

El circuito que he seguido es el siguiente:

<div style="text-align: center"><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_vumetro.jpg"><img  title="esquematico_vumetro" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/esquematico_vumetro.jpg" alt="" width="600" /></a></div>Los esquemáticos del vúmetro, que también he tenido que reducir bastante son los siguientes. La placa tiene unas dimensiones de  60x40mm y las barras de led van por el lado inferior de la placa.
<table align="center">
<tbody>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_schematic.png"><img  title="vumetro_schematic" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_schematic-300x197.png" alt="" width="300" height="197" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_schematic_mon.png"><img  title="vumetro_schematic_mon" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_schematic_mon-300x197.png" alt="" width="300" height="197" /></a></td>
</tr>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_back.png"><img  title="vumetro_back" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_back-300x210.png" alt="" width="300" height="210" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_front.png"><img  title="vumetro_front" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_front-300x210.png" alt="" width="300" height="210" /></a></td>
</tr>
</tbody>
</table>
Podemos ver algunas imágenes del circuito terminado a continuación:
<table align="center">
<tbody>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_front.jpg"><img  title="vumetro_front" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_front-300x231.jpg" alt="" width="300" height="218" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_back.jpg"><img  title="vumetro_back" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/vumetro_back-300x218.jpg" alt="" width="300" height="218" /></a></td>
</tr>
</tbody>
</table>

## Montaje final
Tras montar todo en la caja os dejo algunas imágenes del proyecto acabado que pueden dar algunas ideas sobre el diseño.
<table align="center">
<tbody>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_proceso.jpg"><img  title="etapa_proceso" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_proceso-300x225.jpg" alt="" width="300" height="231" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/ventilador_back.jpg"><img  title="ventilador_back" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/ventilador_back-300x230.jpg" alt="" width="300" height="231" /></a></td>
</tr>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_front.jpg"><img  title="etapa_front" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_front-300x238.jpg" alt="" width="300" height="231" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_back.jpg"><img  title="etapa_back" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_back-300x231.jpg" alt="" width="300" height="231" /></a></td>
</tr>
<tr>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/ventilador_front.jpg"><img  title="ventilador_front" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/ventilador_front-300x240.jpg" alt="" width="300" height="231" /></a></td>
<td><a href="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_final.jpg"><img  title="etapa_final" src="/assets/2011-08-03-como-construir-una-etapa-de-10w/etapa_final-300x225.jpg" alt="" width="300" height="231" /></a></td>
</tr>
</tbody>
</table>
El acabado es bastante bueno y todos los materiales son, como siempre en mis entradas, fáciles de adquirir en cualquier tienda de electrónica. El coste total del proyecto ha sido de unos 55€ aproximádamente.