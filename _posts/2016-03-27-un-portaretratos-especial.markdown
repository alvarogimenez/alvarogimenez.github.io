---
layout: post
title:  "Un portarretratos especial"
date:   2016-03-27 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2016-03-27-un-portaretratos-especial/expo02.jpg"><img align="left" src="/assets/2016-03-27-un-portaretratos-especial/expo02-580x326.jpg" alt="expo02" width="318" height="179" /></a> Cuando era pequeño me encantaba desarmar todo tipo de aparatos electrónicos para después juntar las piezas y construir máquinas sin funcionalidad alguna más allá de mi cabeza. Con el paso de los años fui transformando la extraña afición en un pasatiempos que terminaría ocupando la mayor parte de mi tiempo libre.

Hace poco en mi empresa se inauguró un muro, y cuando digo muro me refiero a un muro de verdad, lo que mi abuela entendería como tal, en el que cada uno podíamos colgar la foto que quisiéramos. Recordé una foto en la que tenía apenas nueve años trasteando con un invento que no sé muy bien qué pretendía ser y decidí darle un poco de significado a la foto construyendo un marco un tanto extravagante.

<!--more-->

<div style="text-align: center">
<video width="640" controls>
  <source src="/assets/2016-03-27-un-portaretratos-especial/photoframe.webm" type="video/webm">
</video>
</div>

La idea era construir una turbina eólica conectada a un generador monofásico que iluminaría una serie de LEDs en la esquina de un pequeño marco de fotos. La salida alterna del generador estaría conectada a un puente rectificador y, más adelante, a un <a title="Ladrón de Julios" href="https://en.wikipedia.org/wiki/Joule_thief">Ladrón de Julios</a> para elevar la tensión a la requerida por el conjunto de LEDS. La entrada de hoy, por tanto, es un reportaje de los pasos que he seguido para construir este peculiar marco de fotos.

## Diseño
El primer paso de todos fue diseñar el marco de fotos y todos los elementos necesarios para la electrónica y el ensamblaje utilizando Autodesk Inventor 2016. Os dejo a continuación un vistazo general, como de costumbre, al diseño ensamblado por completo.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/Design01.png"><img src="/assets/2016-03-27-un-portaretratos-especial/Design01-580x437.png" alt="Design01" width="500" /></a></div>

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/expo01.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/expo01-580x355.jpg" alt="expo01" width="500" /></a></div>

&nbsp;

Los enlaces con los ficheros STL necesarios para imprimir todas las piezas del diseño los dejo a continuación:

&nbsp;
<table>
<tbody>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignPhotoFrame.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignPhotoFrame-580x528.png" alt="DesignPhotoFrame" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/PhotoFrame.stl">PhotoFrame.stl</a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignRotor.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignRotor.png" alt="DesignRotor" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Rotor.stl">Rotor.stl</a></td>
</tr>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignRotorSupport.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignRotorSupport.png" alt="DesignRotorSupport" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/RotorAxisEnd.stl">RotorAxisEnd.stl</a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignStator.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignStator-580x528.png" alt="DesignStator" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Stator.stl">Stator.stl</a></td>
</tr>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignToroidSupport.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignToroidSupport.png" alt="DesignToroidSupport" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/ToroidSupport.stl">ToroidSupport.stl</a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignBoardFrame.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignBoardFrame-580x570.png" alt="DesignBoardFrame" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/BoardFrame.stl">BoardFrame.stl</a></td>
</tr>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignTextBlowHere.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignTextBlowHere-580x324.png" alt="DesignTextBlowHere" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/TextBlowHere.stl">TextBlowHere.stl</a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignTextJouleThief.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignTextJouleThief-580x370.png" alt="DesignTextJouleThief" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/TextJouleThief.stl">TextJouleThief.stl</a></td>
</tr>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DesignFrame.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DesignFrame-580x439.png" alt="DesignFrame" width="110" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Frame001.stl">Frame001.stl</a>
<a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Frame002.stl">Frame002.stl</a>
<a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Frame003.stl">Frame003.stl</a>
<a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/Frame004.stl">Frame004.stl</a></td>
</tr>
</tbody>
</table>

## Construcción de la turbina
Comenzaremos construyendo la turbina utilizando las piezas impresas previamente correspondientes al rotor, el estátor y la pieza de sujeción del rotor. El estátor estará compuesto por ocho bobinas de hilo de cobre esmaltado de 0.1 milímetros de diámetro. Bobinaremos el estátor utilizando un único hilo continuo alternando el sentido del bobinado entre horario y anti-horario para cada eje contiguo.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build01.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build01-580x440.jpg" alt="build01" width="500" /></a></div>

&nbsp;

El rotor contiene series de tres agujeros que utilizaremos para insertar imanes con polarización axial de 5 milímetros de longitud y 2.5 milímetros de diámetro. Del mismo modo que hicimos con cada bobina del estátor, alternaremos la polaridad norte/sur de los imanes en cada grupo contiguo de tres imanes. De esta forma conseguiremos que al girar el rotor dentro del estátor se produzca inducción en el mismo sentido de corriente en las diferentes bobinas.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build02.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build02-580x404.jpg" alt="build02" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build03.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build03-580x383.jpg" alt="build03" width="500" /></a></div>

## Electrónica
La electrónica de este proyecto es muy simple. La primera etapa es un puente rectificador de corriente alterna que he implementado utilizando <a href="https://es.wikipedia.org/wiki/Diodo_Schottky">Diodos Schottky</a>, que tienen una curva I-V menos pronunciada.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/ElectDesignPower.png"><img src="/assets/2016-03-27-un-portaretratos-especial/ElectDesignPower-580x474.png" alt="ElectDesignPower" width="500" /></a></div>

&nbsp;

La segunda etapa es un Ladrón de Julios que utilizaremos para obtener un voltaje de salida superior a la tensión requerida por los LEDs.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/ElectDesignJouleThief.png"><img src="/assets/2016-03-27-un-portaretratos-especial/ElectDesignJouleThief-580x461.png" alt="ElectDesignJouleThief" width="500" /></a></div>

&nbsp;

Utilizando los perfiles adecuados para que los diseños encajen en las piezas impresas se obtienen los siguientes circuitos:

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/ElectPcbJouleThief.png"><img src="/assets/2016-03-27-un-portaretratos-especial/ElectPcbJouleThief-580x545.png" alt="ElectPcbJouleThief" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/ElectPcbLed.png"><img src="/assets/2016-03-27-un-portaretratos-especial/ElectPcbLed-580x579.png" alt="ElectPcbLed" width="500" /></a></div>

Aquí estarían los ficheros DXF para imprimir los positivos de cara a insolar las placas de cobre.
<table>
<tbody>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DxfBouardJouleThief.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DxfBouardJouleThief.png" alt="DxfBouardJouleThief" width="150" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/BoardJouleThief.dxf">BoardJouleThief.dxf</a></td>
</tr>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DxfBouardLed.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DxfBouardLed.png" alt="DxfBouardLed" width="150" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/BoardLed.dxf">BoardLed.dxf</a></td>
</tr>
</tbody>
</table>
Os dejo a continuación algunas fotos del proceso de fabricación de las placas.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build06.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build06-580x308.jpg" alt="build06" width="500" /></a><a href="/assets/2016-03-27-un-portaretratos-especial/build08.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build08-580x372.jpg" alt="build08" width="500" /></a></div>

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build08.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build09-580x413.jpg" alt="build09" width="500" /></a></div>

Para concluir con la electrónica debemos soldar los componentes en las placas. Prometo publicar una entrada sobre todos los pasos para producir placas SMD como esta.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build14.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build14-580x356.jpg" alt="build14" width="500" /><img src="/assets/2016-03-27-un-portaretratos-especial/build15-580x416.jpg" alt="build15" width="500" /></a></div>

## Ensamblaje
Una vez construida la turbina y la electrónica podemos ensamblar el resto del marco. He dividido el marco en varias partes debido a que el área de impresión en mi impresora está limitado a 12x12 centímetros. Para el marco utilizaremos una tabla de aglomerado de 10x15 centímetros y 4 milímetros de grosor.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build04.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build04-580x379.jpg" alt="build04" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build05.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build05-580x417.jpg" alt="build05" width="500" /></a></div>

De cara a guiar los cables por la parte trasera del marco y hacerlo así más elegante deberemos taladrar una serie de agujeros en el contrachapado. Para facilitar esta tarea he exportado una guía que se puede imprimir a escala 1:1 con la señalización de cada agujero en la base.
<table>
<tbody>
<tr>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/DxfHoleGuide.png"><img src="/assets/2016-03-27-un-portaretratos-especial/DxfHoleGuide-580x389.png" alt="DxfHoleGuide" width="200" /></a></td>
<td><a href="/assets/2016-03-27-un-portaretratos-especial/photoframe/HoleGuide.dwg">HoleGuide.dwg</a></td>
</tr>
</tbody>
</table>
Taladraremos los agujeros y fresaremos los canales para facilitar el paso de los cables como muestro en las siguientes imágenes.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build07.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build07-580x326.jpg" alt="build07" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build10.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build10-580x326.jpg" alt="build10" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build11.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build11-580x366.jpg" alt="build11" width="500" /></a></div>

&nbsp;

La placa que sostiene los seis LEDs debería encajar en el orificio situado en la parte trasera de la moldura del marco de fotos. De no hacerlo habría que limarlo hasta que encaje como se muestra en las siguientes imágenes:

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build12.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build12-580x458.jpg" alt="build12" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build13.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build13-580x401.jpg" alt="build13" width="500" /></a></div>

El siguiente paso es realizar las conexiones eléctricas tal y como se muestra en el apartado de Electrónica y soldarlas a la placa principal. No hay problema en que sobre algo de cable porque la moldura de la placa principal está diseñada para poder esconderlo bajo la placa cuando se pegue a la base.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build16.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build16-580x326.jpg" alt="build16" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build17.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build17-580x326.jpg" alt="build17" width="500" /></a></div>

Por último podemos pegar los textos decorativos en los huecos tal y como se muestra en las siguientes imágenes:

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/build18.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build18-580x326.jpg" alt="build18" width="500" /></a> <a href="/assets/2016-03-27-un-portaretratos-especial/build19.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/build19-580x326.jpg" alt="build19" width="500" /></a></div>

&nbsp;

Al girar el rotor debería producirse la suficiente corriente como para iluminar los seis LEDs dispuestos en la esquina del marco de fotos. De ser así habremos concluido el proceso de construcción de este peculiar protarretratos.

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/expo021.jpg"><img src="/assets/2016-03-27-un-portaretratos-especial/expo021-580x326.jpg" alt="expo02" width="500" /></a></div>

Me pregunto qué estaría intentando construir....

<div style="text-align: center"><a href="/assets/2016-03-27-un-portaretratos-especial/foto_pequeno.png"><img src="/assets/2016-03-27-un-portaretratos-especial/foto_pequeno.png" alt="foto_pequeno" width="500" /></a></div>