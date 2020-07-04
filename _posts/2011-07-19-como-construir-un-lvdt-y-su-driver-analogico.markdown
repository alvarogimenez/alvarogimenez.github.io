---
layout: post
title:  "Cómo construir un LVDT y su driver analógico"
date:   2011-07-19 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/legacy/lvdt.png"><img align="left" title="lvdt" src="/assets/legacy/lvdt-300x225.png" alt="" width="300" height="225" /></a>El LVDT es un dispositivo utilizado como transductor de posición lineal en múltiples aplicaciones. Está formado por tres bobinas: una central encargada de la excitación y otras dos laterales que recogerán la información.

Su principio de funcionamiento es sencillo. El LVDT posee un núcleo ferromagnético movil que, al desplazarse, cambia la inductancia entre la bobina central y las dos laterales provocando que el voltaje inducido en ambas cambie de manera proporcional al desplazamiento del núcleo. Generalmente el núcleo estará unido al elemento cuya posición lineal queremos medir y, dado que no se necesita contacto alguno con el dispositivo, el LVDT no aporta fricción al sistema siendo, por tanto, un excelente transductor en comparación a medidores resistivos y otros tipos.

<!--more-->

Nuestro objetivo es construir un dispositivo que tendrá dos funciones: alimentar el bobinado central e interpretar los datos de los bobinados laterales para finalmente proporcionar un voltaje de corriente continua que represente la posición del núcleo.

Para comprender mejor el funcionamiento del LVDT he montado una pequeña aplicación donde se aprecian, al mover el núcleo a lo largo de su eje con el ratón, las variaciones en los voltajes de las diferentes bobinas.
<object id="lvdt" width="550" height="400" classid="clsid:d27cdb6e-ae6d-11cf-96b8-444553540000" codebase="http://download.macromedia.com/pub/shockwave/cabs/flash/swflash.cab#version=6,0,40,0" align="middle"><param name="quality" value="high" /><param name="play" value="true" /><param name="loop" value="true" /><param name="wmode" value="window" /><param name="scale" value="showall" /><param name="menu" value="true" /><param name="devicefont" value="false" /><param name="salign" /><param name="allowScriptAccess" value="sameDomain" /><param name="src" value="/assets/legacy/lvdt.swf" /><param name="allowscriptaccess" value="sameDomain" /><embed id="lvdt" width="550" height="400" type="application/x-shockwave-flash" src="/assets/legacy/lvdt.swf" quality="high" play="true" loop="true" wmode="window" scale="showall" menu="true" devicefont="false" allowScriptAccess="sameDomain" allowscriptaccess="sameDomain" align="middle" /></object>

Como se puede observar en la aplicación la bobina primaria, de color rojo, recibe una excitación continua en forma de seno lo que provoca un voltaje inducido en las dos bobinas de los laterales. Vemos que al desplazar hacia los lados el núcleo cambia la amplitud de la onda inducida en las dos bobinas secundarias.

Podemos apreciar también que si realizamos el cálculo matemático sencillo de restar las amplitudes de las dos ondas obtenemos un nivel de CC que representa, de forma lineal, la posición del núcleo. Ese es uno de nuestros objetivos junto con excitar, a partir de un voltaje continuo también, la bobina principal.

Queremos entonces un dispositivo analógico que reciba una tensión continua y proporcione otra tensión también continua en función de la posición del núcleo. Para ello separaremos el proyecto en dos partes: el excitador y el analizador.

## Generador de onda
Para excitar la bobina primaria utilizaremos un oscilador sinsoidal por rotación de fase y un buffer para asegurar que la tensión no caiga al alimentar bobinas de baja impedancia. Veamos el esquemático que he diseñado para el excitador:
<p style="text-align: left;"><div style="text-align: center"><a href="/assets/legacy/schematic_exc.png"><img  title="schematic_exc" src="/assets/legacy/schematic_exc-1024x838.png" alt="" width="512" height="418" /></a></div></p>
<p style="text-align: left;">Como vemos en la izquierda, con el primer OPAMP, he montado un oscilador cuya frecuencia es de aproximadamente 620Hz. Su frecuencia teórica es la siguiente:</p>
<p style="text-align: left;">\[\Large f_\mathrm{osc}=\frac{1}{2\pi RC\sqrt{2N}}=\frac{1}{2\pi 1000\cdot 100\cdot 10^{-9}\sqrt{2\cdot 3}}=649 Hz\]</p>
<p style="text-align: left;">Seguido al oscilador hay un potenciometro utilizado para ajustar el voltaje de salida al deseado. Utilizaremos un voltaje de 2V RMS normalmente.</p>
<p style="text-align: left;">Por último he puesto un buffer con dos transistores NPN y PNP para aumentar la capacidad de corriente de salida del circuito dado que alimentaremos bobinas, típicamente, de unos pocos ohmios.</p>

<h2 style="text-align: left;">Análisis de secundarios</h2>
Sabemos que las dos bobinas secundarias proporcionaran un voltaje inducido por la primaria que también será de forma sinusoidal. En primer lugar tendremos que convertir dicha onda sinusoidal a una tensión constante a la altura de su amplitud. Para realizar esto utilizaremos una pequeña modificación del <a href="http://en.wikipedia.org/wiki/Precision_rectifier">super diodo </a>que permite mantener el máximo de una señal.

<div style="text-align: center"><a href="/assets/legacy/schematic_superdiodo.png"><img  title="schematic_superdiodo" src="/assets/legacy/schematic_superdiodo-300x261.png" alt="" width="300" height="261" /></a></div>

Una vez hemos rectificado las señales de las dos bobinas secundarias las restaremos con otro OPAMP y posteriormente añadiremos una etapa de ajuste para permitir al usuario ajustar el cero del dispositivo de manera precisa.

Veamos el circuito completo:

## <div style="text-align: center"><a href="/assets/legacy/schematic_out.png"><img  title="schematic_out" src="/assets/legacy/schematic_out-1024x742.png" alt="" width="640" height="463" /></a></div>
Observamos los dos amplificadores de la izquierda cuya función es rectificar la onda y obtener su nivel de pico cuyas salidas se dirigen a un circuito restador. A la salida de dicho circuito deberíamos tener la onda que esperamos, sin embargo a veces las bobinas de las LVDT no están bien calibradas (no tienen el mismo número de vueltas o longitud) de modo que el cero no coincide con la posición central del núcleo. Para solucionar esto se ha incluido un nuevo restador que permite ajustar el nivel nulo con un potenciómetro.

## Esquemáticos y listado de componentes
El circuito que he diseñado tiene unas dimensiones de 100x120mm. El esquemático del driver del LVDT es el siguiente:
<table align="center">
<tbody>
<tr>
<td><a href="/assets/legacy/esquematico.png"><img  title="esquematico" src="/assets/legacy/esquematico-255x300.png" alt="" width="255" height="300" /></a></td>
<td><a href="/assets/legacy/esquematico_mono.png"><img  title="esquematico_mono" src="/assets/legacy/esquematico_mono-255x300.png" alt="" width="255" height="300" /></a></td>
</tr>
</tbody>
</table>
<p style="text-align: left;">Listado de componentes:</p>

<table align="center">
<tbody>
<tr>
<td width="150"><span style="text-decoration: underline;"><strong>Referencia</strong></span></td>
<td><span style="text-decoration: underline;"><strong>Valor</strong></span></td>
</tr>
<tr>
<td>R1</td>
<td>33k</td>
</tr>
<tr>
<td>R2,R3,R4</td>
<td>1k</td>
</tr>
<tr>
<td>R5-12,R15</td>
<td>10k</td>
</tr>
<tr>
<td>R13,R14</td>
<td>22k</td>
</tr>
<tr>
<td>U1,U2</td>
<td>TL084</td>
</tr>
<tr>
<td>D1,D2,D3</td>
<td>1N4148</td>
</tr>
<tr>
<td>C1,C2,C3</td>
<td>100nF</td>
</tr>
<tr>
<td>C4</td>
<td>220nF</td>
</tr>
<tr>
<td>C5,C6</td>
<td>10uF</td>
</tr>
<tr>
<td>Q1</td>
<td>TIP31</td>
</tr>
<tr>
<td>Q2</td>
<td>TIP32</td>
</tr>
<tr>
<td>RV1,RV2</td>
<td>Potenciómetro 10K (Ajuste vertical)</td>
</tr>
</tbody>
</table>
El esquemático completo del proyecto es el siguiente:

<div style="text-align: center"><a href="/assets/legacy/schematic.png"><img  title="schematic" src="/assets/legacy/schematic-1024x583.png" alt="" width="640" height="364" /></a></div>

## Resultados del proyecto
Tras montar el circuito anterior he grabado un video donde se observan los resultados del proyecto. Espero que haya sido de utilidad o al menos interesante para el lector. Proximamente trabajaré sobre otros transductores algo más sencillos y también bastante eficaces.

<iframe src="http://www.youtube.com/embed/arhLqh5bLGI" frameborder="0" width="425" height="349"></iframe>

Algunas imágenes del prototipo:

<table>
<tr>
<td>
<a href="/assets/legacy/P7210268.jpg"><img  title="LVDT" src="/assets/legacy/P7210268-300x228.jpg" alt="" width="280" height="225" /></a>
</td>
<td>
<a href="/assets/legacy/P7210269.jpg"><img  title="LVDT" src="/assets/legacy/P7210269-300x219.jpg" alt="" width="280" height="225" /></a>
</td>
</tr>
<tr>
<td>
<a href="/assets/legacy/P7210280.jpg"><img  title="LVDT" src="/assets/legacy/P7210280-300x225.jpg" alt="" width="280" height="225" /></a>
</td>
<td>
<a href="/assets/legacy/P7210281.jpg"><img  title="LVDT" src="/assets/legacy/P7210281-300x227.jpg" alt="" width="280" height="225" /></a>
</td>
</tr>
</table>