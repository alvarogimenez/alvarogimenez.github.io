---
layout: post
title:  "Construyendo un Zoótropo 3D"
date:   2015-04-06 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2015-04-06-construyendo-un-zootropo-3d/main.jpg"><img align="left" src="/assets/2015-04-06-construyendo-un-zootropo-3d/main-580x561.jpg" alt="main" width="251" height="243" /></a>
Los zoótropos son máquinas destinadas a mostrar imágenes en movimiento a partir de fotogramas individuales. Este concepto, precursor de lo que hoy en día conocemos como cine, fue utilizado inicialmente con tambores giratorios decorados con una secuencia de fotogramas dibujados en el fondo  que, al hacerlos girar, mostraban una imagen en movimiento a través de una serie de ranuras aprovechando un efecto óptico.

Una evolución natural de los zoótropos clásicos es el zoótropo en 3D. Este tipo de zoótropo utiliza modelos en 3D que forman una secuencia o animación. Utilizando una luz que se enciende a intervalos regulares durante pequeñas fracciones de segundo se crea el efecto estroboscópico y se da la sensación de una imagen en movimiento.

Existe una gran variedad de zoótropos en 3D y así como técnicas para diseñarlos y construirlos. Lo que hoy traigo es el diseño que he realizado de un zoótropo en 3D y los pasos detallados que he seguido para su implementación.

<!--more-->

<div style="text-align: center">
    <video width="640" controls>
    <source src="/assets/2015-04-06-construyendo-un-zootropo-3d/main.webm" type="video/webm">
    </video>
</div>


## Diseño

<a href="/assets/2015-04-06-construyendo-un-zootropo-3d/design.jpg"><img align="left" src="/assets/2015-04-06-construyendo-un-zootropo-3d/design-580x554.jpg" alt="design" width="252" height="241" /></a>
El diseño que he realizado de mi particular zoótropo es, como se aprecia en la imagen lateral, un hexágono acristalado por los laterales y en la parte superior. En el interior del hexágono se situará un rotor que hará girar el disco con los objetos de la animación y una serie de LEDs para conseguir el efecto estroboscópico.

Una de las limitaciones del efecto estroboscópico cuando la intensidad de la fuente de luz no es suficiente es que, si no hay suficiente oscuridad, se puede apreciar el movimiento. Como mejor se aprecia el efecto de un zoótropo de estas características es cuando la única luz que incide sobre el objeto es la luz que crea el efecto. Para conseguir esto he utilizado cristales tintados (que he tintado yo mismo) de cara a que no entre nada de luz al sistema y la animación aparezca al encender la luz de forma interna.

El corazón del diseño es la base central diseñada para alojar un motor de 25 milímetros de diámetro y el interruptor óptico H21A1. El motor está situado a uno de los laterales para permitir reducción de movimiento utilizando un engranaje situado en el rotor que veremos más adelante.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/base_inventor.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/base_inventor-580x389.jpg" alt="base_inventor" width="380" height="255" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/base_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/base_real-580x326.jpg" alt="base_real" width="381" height="214" /></a></div>

El agujero situado en el centro de la base está diseñado con un diámetro de 2.8 milímetros, justo para encajar un eje de 3 milímetros sobre el que girará el rotor. La longitud de dicho eje no es crítica, bastará con que sobresalga al menos 2 centímetros de la base.

El rotor es la otra pieza clave del diseño. Está formado, por un lado, por una plataforma sobre la que se puede anclar el disco de la animación y, por otro lado, un engranaje interior y una serie de barreras y huecos para interrumpir el flujo de luz en el H21A1.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_inventor_top.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_inventor_top-580x389.jpg" alt="rotor_inventor_top" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_inventor_bottom.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_inventor_bottom-580x390.jpg" alt="rotor_inventor_bottom" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_real_top.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_real_top-580x326.jpg" alt="rotor_real_top" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_real_bottom.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/rotor_real_bottom-580x326.jpg" alt="rotor_real_bottom" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
Como se observa en las imágenes anteriores, el número de pasos definido en las láminas que bloquean la luz en el interruptor es ocho. Esto implica que la cantidad de fotogramas con los que podremos animar el objeto está limitado a dicha cifra.

Tanto el engranaje que lleva el motor (Cuyo eje será de 2 milímetros) como el engranaje exterior situado en la base del rotor son de módulo 1. La razón de escoger este módulo y no uno más pequeño son las limitaciones de precisión por parte de la impresora (He podido comprobar que este módulo es el mínimo viable con esta herramienta). El número de dientes (y por tanto el diámetro al ser de módulo 1) del engranaje exterior es de 75 frente al número de dientes del engranaje interior que es de 8, resultando en un ratio de 9.375. Esta reducción permitirá aprovechar la fuerza del motor sin que la velocidad del rotor sea excesiva, produciendo animaciones aceleradas y borrosas.

Antes de profundizar en el diseño de cada pieza del zoótropo veamos una imagen general del diseño con la finalidad de entender la dirección de los siguientes pasos:
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/full_inventor_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/full_inventor_front-580x379.jpg" alt="full_inventor_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/full_inventor_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/full_inventor_back-580x379.jpg" alt="full_inventor_back" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/full_real_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/full_real_front-580x326.jpg" alt="full_real_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/full_real_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/full_real_back-580x326.jpg" alt="full_real_back" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
La pieza que define la carcasa es la base donde estará situado tanto el armazón del motor como la electrónica y la batería. La base contiene un hueco rectangular de las dimensiones justas para alojar una batería de 9 voltios.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_inventor_top.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_inventor_top-580x366.jpg" alt="framebase_inventor_top" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_inventor_bottom.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_inventor_bottom-580x366.jpg" alt="framebase_inventor_bottom" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_real_top.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_real_top-580x326.jpg" alt="framebase_real_top" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_real_bottom.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framebase_real_bottom-580x326.jpg" alt="framebase_real_bottom" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
De cara a poder ensamblar la tapa de la base he diseñado tres orificios con espacio para alojar una tuerca M3 de 2.55 milímetros de de ancho. Para fijar dicha tuerca se colocarán unos discos sobre ellas utilizando pegamento. La tapa de la base tiene el siguiente aspecto:
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framecover_inventor.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framecover_inventor-580x403.jpg" alt="framecover_inventor" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/batterycover_inventor.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/batterycover_inventor-580x403.jpg" alt="batterycover_inventor" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/framecover_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/framecover_real-580x326.jpg" alt="framecover_real" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/batterycover_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/batterycover_real-580x326.jpg" alt="batterycover_real" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
Las paredes estarán divididas, al igual que la tapa, en dos partes debido a las limitaciones del área de impresión, que permiten como máximo objetos de 12 x 12 centímetros. La pared frontal tiene tres huecos en la parte superior destinados a alojar los cristales tintados que tendrán un tamaño de 52 x 53 milímetros (Caprichosa medida por un fallo de diseño). Los huecos rectangulares de la parte inferior contendrán paneles decorativos que veremos más adelante.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/front_inventor_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/front_inventor_front-580x398.jpg" alt="front_inventor_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/front_inventor_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/front_inventor_back-580x398.jpg" alt="front_inventor_back" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/front_real_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/front_real_front-580x325.jpg" alt="front_real_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/front_real_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/front_real_back-580x326.jpg" alt="front_real_back" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
La parte superior sigue el mismo concepto: dos huecos rectangulares para los cristales tintados y otros dos huecos en la parte inferior para los paneles de decoración.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/back_inventor_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/back_inventor_front-580x385.jpg" alt="back_inventor_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/back_inventor_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/back_inventor_back-580x385.jpg" alt="back_inventor_back" width="290" height="163" /></a></div></td>
</tr>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/back_real_front.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/back_real_front-580x326.jpg" alt="back_real_front" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/back_real_back.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/back_real_back-580x326.jpg" alt="back_real_back" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
Como vemos la parte central de esta pieza no tiene espacio para cristales a cambio de contener los agujeros para el interruptor de encendido y el potenciómetro para regular la velocidad de la animación. Vemos que contiene también la base de la bisagra para la tapa que, como se observa, está seccionada por uno de los laterales de modo que el lateral sobrante pueda ser incorporado y pegado una vez ensamblada la tapa.

Los paneles decorativos, a los que hacía referencia anteriormente, están diseñados utilizando como motivo los paneles de difusión acústica utilizados en los estudios de sonido. De cara a evitar repeticiones he diseñado dos tipos distintos de panel que vemos a continuación:
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_autodesk1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_autodesk1-580x382.jpg" alt="decopanel_autodesk1" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_autodesk2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_autodesk2-580x382.jpg" alt="decopanel_autodesk2" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/decopanel_real-580x326.jpg" alt="decopanel_real" width="580" height="326" /></a></div>

La última pieza importante del diseño del hexágono es la tapa. Al igual que los paneles frontal y trasero está dividida en dos partes y ambas, al juntarse, dejan espacio para colocar el cristal hexagonal de la superficie.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/frametop_inventor.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/frametop_inventor-580x417.jpg" alt="frametop_inventor" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/frametop_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/frametop_real-580x326.jpg" alt="frametop_real" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
La parte final del diseño está protagonizada por la animación que dará vida al zoótropo. Esta animación consistirá en una figura humana caminando en 8 fotogramas individuales situados en un disco que se colocará sobre el rotor que vimos previamente.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/figures_autodesk.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/figures_autodesk.jpg" alt="figures_autodesk" width="580" /><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/figures_real_2-580x326.jpg" alt="figures_real_2" width="580" height="326" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/figures_real_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/figures_real_1-580x326.jpg" alt="figures_real_1" width="580" height="326" /></a></div>

&nbsp;

## Impresión y pintura
En total el diseño contiene 31 piezas (25 modelos). El tiempo de impresión aproximado es de 26 horas con una precisión de capa de 0.20 milímetros (Aunque para algunas piezas del interior se utilizó una precisión menor). A continuación muestro una lista con todas las piezas y los ficheros STL correspondientes:
<table>
<tbody>
<tr>
<td><b>Ref.</b></td>
<td><strong>Cantidad</strong></td>
<td><strong>Descripción</strong></td>
<td><strong>Tiempo de impresión</strong></td>
<td><strong>STL</strong></td>
</tr>
<tr>
<td>A01</td>
<td>1</td>
<td>Base del Rotor</td>
<td>1h 05m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/A01.stl">A01.stl</a></td>
</tr>
<tr>
<td>A02</td>
<td>1</td>
<td>Rotor</td>
<td>1h 52m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/A02.stl">A02.stl</a></td>
</tr>
<tr>
<td>A03</td>
<td>1</td>
<td>Engranaje del motor</td>
<td>04m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/A03.stl">A03.stl</a></td>
</tr>
<tr>
<td>B01</td>
<td>1</td>
<td>Base del hexágono</td>
<td>4h 06m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B01.stl">B01.stl</a></td>
</tr>
<tr>
<td>B02</td>
<td>1</td>
<td>Frontal del hexágono</td>
<td>4h 58m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B02.stl">B02.stl</a></td>
</tr>
<tr>
<td>B03</td>
<td>1</td>
<td>Trasera del hexágono</td>
<td>5h 34m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B03.stl">B03.stl</a></td>
</tr>
<tr>
<td>B04</td>
<td>1</td>
<td>Frontal de la tapa</td>
<td>45m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B04.stl">B04.stl</a></td>
</tr>
<tr>
<td>B05</td>
<td>1</td>
<td>Trasera de la tapa</td>
<td>56m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B05.stl">B05.stl</a></td>
</tr>
<tr>
<td>B06</td>
<td>1</td>
<td>Sección lateral de la bisagra</td>
<td>04m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B06.stl">B06.stl</a></td>
</tr>
<tr>
<td>B07</td>
<td>1</td>
<td>Cubierta inferior</td>
<td>2h 41m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B07.stl">B07.stl</a></td>
</tr>
<tr>
<td>B08</td>
<td>1</td>
<td>Tapa del porta pilas</td>
<td>17m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/B08.stl">B08.stl</a></td>
</tr>
<tr>
<td>P01</td>
<td>2</td>
<td>Panel decorativo 1</td>
<td>22m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/P01.stl">P01.stl</a></td>
</tr>
<tr>
<td>P02</td>
<td>3</td>
<td>Panel decorativo 2</td>
<td>23m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/P02.stl">P02.stl</a></td>
</tr>
<tr>
<td>C01</td>
<td>1</td>
<td>Animación 1</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C01.stl">C01.stl</a></td>
</tr>
<tr>
<td>C02</td>
<td>1</td>
<td>Animación 2</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C02.stl">C02.stl</a></td>
</tr>
<tr>
<td>C03</td>
<td>1</td>
<td>Animación 3</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C03.stl">C03.stl</a></td>
</tr>
<tr>
<td>C04</td>
<td>1</td>
<td>Animación 4</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C04.stl">C04.stl</a></td>
</tr>
<tr>
<td>C05</td>
<td>1</td>
<td>Animación 5</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C05.stl">C05.stl</a></td>
</tr>
<tr>
<td>C06</td>
<td>1</td>
<td>Animación 6</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C06.stl">C06.stl</a></td>
</tr>
<tr>
<td>C07</td>
<td>1</td>
<td>Animación 7</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C07.stl">C07.stl</a></td>
</tr>
<tr>
<td>C08</td>
<td>1</td>
<td>Animación 8</td>
<td>28m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C08.stl">C08.stl</a></td>
</tr>
<tr>
<td>C09</td>
<td>1</td>
<td>Base de la animación</td>
<td>1h 21m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/C09.stl">C09.stl</a></td>
</tr>
<tr>
<td>D01</td>
<td>4</td>
<td>Tapa para agujero de tuerca</td>
<td>2m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/D01.stl">D01.stl</a></td>
</tr>
<tr>
<td>D02</td>
<td>1</td>
<td>Mando del potenciómetro</td>
<td>20m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/D02.stl">D02.stl</a></td>
</tr>
<tr>
<td>D03</td>
<td>1</td>
<td>Tope de fijación del rotor al eje</td>
<td>20m</td>
<td><a href="http://www.j0k3n.com/src/zoetrope/D02.stl">D03.stl</a></td>
</tr>
</tbody>
</table>
Una vez impresas todas las piezas he utilizado pintura en spray para pintar algunas de ellas. Concretamente he pintado las piezas que tienen visibilidad exterior dado que el interior es deseable que continúe siendo negro de cara a que lo único que se vea al encenderse la luz sea el objeto animado. En caso de que el lector disponga de filamento de otro color, comúnmente blanco, recomiendo pintar el interior de negro por el mismo motivo.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/paint.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/paint-580x326.jpg" alt="paint" width="580" height="326" /></a></div>

En mi caso he escogido el color blanco para el exterior del objeto y el azul cobalto para los paneles decorativos. Tras proteger las zonas que no debían ser pintadas y varias capas de pintura, este es el resultado de algunas de las piezas:
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/colorpiece1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/colorpiece1-580x326.jpg" alt="colorpiece1" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/colorpiece2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/colorpiece2-580x326.jpg" alt="colorpiece2" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
Las piezas de la animación pueden quedar imprecisas debido a que no son de gran tamaño. En ese caso se puede utilizar acetona pura para pulirlas y así obtener un resultado más homogéneo:
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/smo1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/smo1-580x326.jpg" alt="smo1" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/smo2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/smo2-580x326.jpg" alt="smo2" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/smo3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/smo3-580x326.jpg" alt="smo3" width="580" height="326" /></a></div>

## Electrónica
Otra de las partes importantes de este proyecto es la electrónica utilizada. He querido que todo el control de velocidad y del efecto de luz se realice únicamente con componentes analógicos por lo que el protagonista principal es el integrado 555.

El control de la animación está divida en dos partes: el control de la velocidad del motor y la regulación del lapso de tiempo de encendido de la luz para lograr el efecto estroboscópico.

El control de velocidad del motor lo realizamos utilizando el 555 como generador Modulación por Ancho de Pulsos o PWM. A la salida del 555 he colocado un TIP31 y un diodo protector para cubrir la necesidad de corriente del motor.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_pwm.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_pwm-580x587.jpg" alt="schematic_pwm" width="580" height="587" /></a></div>

Se puede observar que hay tres potenciómetros. Dos de ellos son para regular el mínimo y máximo de velocidad del motor en las posiciones extremo del potenciómetro. El restante regulará la velocidad en sí en el intervalo definido por los dos anteriores.

La interfaz entre el H21A1 y el 555 contendrá un transistor adicional de cara a mantener el nivel de tensión cerca del nivel de alimentación. Dado que el circuito lo vamos a alimentar con 9 voltios, el diodo emisor del interruptor lo protegemos con una resistencia de 1K.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_h21a1_interface.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_h21a1_interface.jpg" alt="schematic_h21a1_interface" width="434" height="389" /></a></div>

Llegados a este punto tenemos, en la salida de la interfaz del H21A1, una bajada de flanco cada vez que una de las barreras del rotor se interpone en la línea de emisión de luz del interruptor. El problema es que el tiempo que permanece la señal a cero es demasiado largo y dependiente de la velocidad de la animación y, por tanto, no la podemos utilizar para decidir directamente el encendido y apagado de los LEDs.

Lo que queremos es que en cada bajada de flanco por parte del H21A1 se genere un pulso positivo de ancho controlado y definido independientemente del ancho de pulso de entrada. Para ello utilizaremos el 555 en configuración monoestable como vemos a continuación:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_monostable.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_monostable-580x435.jpg" alt="schematic_monostable" width="580" height="435" /></a></div>

El tiempo del ancho de pulso de un 555 en esta configuración viene dado por la siguiente expresión:

\[Tp = 1.1*R*C\]

Utilizando los valores en el esquemático anterior tenemos que:

\[Tp = 1.1*1000*10*10^{-6} = 0.011 \text{ segundos (11 milisegundos)}\]

Vemos en la siguiente imagen la duración del pulso de encendido de los LED a la salida del 555 (En azul) frente a la duración del pulso en estado bajo del H21A1 (En rojo). Se observa que la duración del pulso de encendido es de, efectivamente, 11 milisegundos (La cuadrícula es de 10 milisegundos):

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse-580x274.jpg" alt="graph_pulse" width="580" height="274" /></a></div>

Existe un problema al utilizar el 555 como monoestable y es que el ancho del pulso de entrada debe ser inferior al ancho de pulso de salida. Esto es precisamente lo contrario a lo que hemos dicho que sucedía: El ancho de pulso de entrada será típicamente superior al ancho de pulso de salida.

Para solucionar este problema he utilizado un filtro para derivar la señal. Al derivar un escalón obtenemos un impulso que alcanzará el valor suficiente como para activar el disparador del 555. Vemos a continuación cuál es el efecto de colocar esta etapa entre la interfaz del H21A1 y el disparador del 555.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse_without_diode.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse_without_diode-580x288.jpg" alt="graph_pulse_without_diode" width="580" height="288" /></a></div>

Como se observa, cuando el pulso de salida del H21A1 (Rojo) vuelve a su estado alto se produce el mismo efecto a la entrada del 555 (Azul), generando un pico de voltaje por encima de la tensión deseada. Para evitar este voltaje se ha utilizado eldiodo D4 en paralelo a R6. Al colocar el diodo el único impulso que persiste es el que necesitamos para activar el 555 durante el flanco de bajada (Nótese que he cambiado la escala vertical):

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse_with_diode.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/graph_pulse_with_diode-580x270.jpg" alt="graph_pulse_with_diode" width="580" height="270" /></a></div>

Las matrices de LEDs, mencionadas anteriormente, están diseñadas para limitar los diodos a 20 mA utilizando resistencias de 330 ohmios. Vemos el esquemático a continuación:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_ledarray.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/schematic_ledarray.jpg" alt="schematic_ledarray" width="452" height="476" /></a></div>

Dado que el espacio en la base del hexágono es reducido he tenido que aprovecharlo al máximo. Para ello he diseñado la placa para encajar con las paredes del hexágono tal y como se muestra en la siguiente imagen:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_inventor.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_inventor-580x408.jpg" alt="pcb_inventor" width="552" height="388" /></a></div>

La placa diseñada tiene el siguiente aspecto:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_proteus.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_proteus-580x308.jpg" alt="pcb_proteus" width="580" height="308" /><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_real-580x326.jpg" alt="pcb_real" width="580" height="326" /></a></div>

Las matrices de LEDs son dos copias del mismo diseño, nuevamente pensado para encajar en las partes lisas de las esquinas del frontal del hexágono:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_proteus.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_proteus-580x299.jpg" alt="pcb_led_proteus" width="450" height="232" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_real.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_real-580x326.jpg" alt="pcb_led_real" width="450" height="253" /></a></div>

A continuación dejo los enlaces para descargar los fotolitos de ambas placas.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_ares.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_ares-580x373.jpg" alt="pcb_ares" width="580" height="373" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_ares.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_led_ares-580x200.jpg" alt="pcb_led_ares" width="580" height="200" /></a></div>

El listado de componentes es el siguiente:
<table>
<tbody>
<tr>
<td><strong>Cantidad</strong></td>
<td><strong>Descripción</strong></td>
<td><strong>Referencias</strong></td>
</tr>
<tr>
<td>4</td>
<td>Resistencia 1K</td>
<td>R1,R3,R5,R7</td>
</tr>
<tr>
<td>2</td>
<td>Resistencia 10K</td>
<td>R4,R6</td>
</tr>
<tr>
<td>14</td>
<td>Resistencia 330R</td>
<td>R2,R8 &amp; (R1 a R6 LEDs)</td>
</tr>
<tr>
<td>2</td>
<td>Potenciómetro 100K Ajuste vert.</td>
<td>RV1, RV2</td>
</tr>
<tr>
<td>2</td>
<td>Potenciómetro 100K Eje Panel</td>
<td>POT</td>
</tr>
<tr>
<td>3</td>
<td>Condensador 10nF</td>
<td>C1,C3,C4</td>
</tr>
<tr>
<td>1</td>
<td>Condensador 100nF</td>
<td>C2</td>
</tr>
<tr>
<td>1</td>
<td>Condensador 10uF</td>
<td>C5</td>
</tr>
<tr>
<td>1</td>
<td>Condensador 470uF</td>
<td>C6</td>
</tr>
<tr>
<td>2</td>
<td>Diodo 1N4148</td>
<td>D1,D2,D3,D4</td>
</tr>
<tr>
<td>2</td>
<td>555</td>
<td>U1,U2</td>
</tr>
<tr>
<td>1</td>
<td>Transistor BC548C</td>
<td>Q2</td>
</tr>
<tr>
<td>2</td>
<td>Transistor TIP31</td>
<td>Q1,Q3</td>
</tr>
<tr>
<td>12</td>
<td>Led Blanco 5mm</td>
<td>D1 a D6 en LEDs</td>
</tr>
</tbody>
</table>
Una vez reveladas las placas y conectadas a los componentes principales es el momento de probar que todo funciona como debe.

[WebM/GIF: Video del test con la placa de control]

## Ensamblaje de las piezas
Comenzaremos ensamblando la parte central del zoótropo. En primer lugar montaremos el motor y el H21A1 en la base correspondiente como vemos en la siguiente imagen:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_inventor_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_inventor_1-580x368.jpg" alt="assembly_inventor_1" width="580" height="368" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_1-580x326.jpg" alt="assembly_real_1" width="580" height="326" /></a></div>

Tanto el soporte del H21A1 como el soporte del motor tienen hueco para pasar los cables hacia la base de la caja. Deberemos dejar cable suficiente para poder soldarlo después a la placa de control con cierta comodidad.

Antes de colocar los paneles laterales sobre la base es recomendable incorporar y pegar todos los paneles decorativos. Queda espacio para meterlos aún haciendo esto en un paso posterior pero es más cómodo y nada impide hacerlo ahora.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_2-580x326.jpg" alt="assembly_real_2" width="580" height="326" /></a></div>

Una vez hecho esto comenzaremos incorporando el panel frontal a la base. Existe un pequeño escalón en la base que facilitará el ensamblaje. Debería coincidir el perfil del panel lateral con el escalón. Tras comprobarlo aplicaremos pegamento a lo largo de la zona de contacto y uniremos fuertemente ambas partes.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_inventor_3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_inventor_3-580x385.jpg" alt="assembly_inventor_3" width="580" height="385" /></a> <a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_3-580x326.jpg" alt="assembly_real_3" width="580" height="326" /></a></div>

El panel posterior lo uniremos del mismo modo, esta vez aplicando el pegamento también a la zona de contacto lateral, que forma los ejes laterales del hexágono.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_4.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_4-580x326.jpg" alt="assembly_real_4" width="580" height="326" /></a></div>

Es el momento de cortar y tintar los cristales. He utilizado cristales de marcos de fotos que tienen un grosor aceptable y dentro de los límites del hueco en los paneles laterales.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_1-580x326.jpg" alt="glasscut_1" width="580" height="326" /></a></div>

Desde aquí mis más profundo respeto y admiración a todos aquellos cuya profesión o habilidad comprenda el corte de cristales. Jamás pensé que cortar unos cristales iba a ser más complicado que revelar y soldar una PCB.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_2-580x326.jpg" alt="glasscut_2" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_3-580x326.jpg" alt="glasscut_3" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_4.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glasscut_4-580x326.jpg" alt="glasscut_4" width="580" height="326" /></a></div>

Para tintar los cristales he utilizado una lámina autoadhesiva como la que se utiliza al tintar las lunas de los vehículos. Tras retirar el protector plástico de la lámina, mojar con agua el cristal uniformemente y colocar con cuidado la misma sobre los cristales el resultado es el siguiente:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_1-580x326.jpg" alt="glass_stk_1" width="580" height="326" /></a></div>
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_2-580x326.jpg" alt="glass_stk_2" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_stk_3-580x326.jpg" alt="glass_stk_3" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
Dado que los cristales aún están húmedos por el agua que hemos aplicado es posible eliminar las burbujas de modo que el acabado sea uniforme. Antes de colocar los cristales procedemos a unir la tapa del hexágono. No hacen falta muchas indicaciones, creo que es bastante intuitivo:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/cover_with_glass.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/cover_with_glass-580x326.jpg" alt="cover_with_glass" width="580" height="326" /></a></div>

Los cristales los podemos fijar de muchas formas. Yo he decidido utilizar pegamento termofusible en las esquinas de modo que se puedan retirar en caso de ser necesario. Vemos algunas imágenes a continuación:

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_finish.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/glass_finish-580x326.jpg" alt="glass_finish" width="580" height="326" /></a></div>

Podemos ya dar la vuelta al hexágono y proceder al montaje de la circuitería. Cortaremos y soldaremos en primer lugar los cables del H21A1 y el motor. Es posible que, si ya se ha colocado la base del rotor, haya que retirarla y volverla a colocar nuevamente con la placa dado que reutiliza los mismos tornillos.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_fixed.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/pcb_fixed-580x326.jpg" alt="pcb_fixed" width="580" height="326" /></a></div>

La base del hexágono está dotada de agujeros para sacar los cables que deben comunicar con el interior de la caja. Sacaremos dos pares de cables por los dos agujeros frontales para las dos matrices de led y el cable del interruptor de encendido y el potenciómetro por el agujero trasero más cercano a los huecos para dichos controles.

Una vez tenemos los cables comunicando con el interior de la caja podemos colocar las matrices de LEDs, el interruptor y el potenciómetro. Es aconsejable realizar una prueba conectando el potenciómetro sin soldar para comprobar en qué sentido de giro queremos que aumente o disminuya la velocidad.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_5.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_5-580x326.jpg" alt="assembly_real_5" width="580" height="326" /><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_6-580x326.jpg" alt="assembly_real_6" width="580" height="326" /></a></div>

En este momento podemos colocar la tapa. Para que la tapa quede permanentemente fija al resto de la estructura podemos utilizar la pieza de sección de la bisagra pegándola en el lugar correspondiente.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/cover_helper.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/cover_helper-580x326.jpg" alt="cover_helper" width="580" height="326" /></a></div>

El siguiente paso es colocar las figuras de la animación en la base giratoria y atornillar la misma al rotor. Nótese que, dependiendo de como hayamos soldado el motor la estructura girará en un sentido u en otro y esto se ha de tener en cuenta en el sentido de colocación de los pasos de la animación.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_1.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_1-580x326.jpg" alt="animdisk_1" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_2.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_2-580x326.jpg" alt="animdisk_2" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_3.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/animdisk_3-580x326.jpg" alt="animdisk_3" width="580" height="326" /></a></div>

Colocaremos ahora la tapa inferior para proteger la electrónica y la tapa de la batería para mantenerla en su sitio.
<table>
<tbody>
<tr>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_7.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_7-580x326.jpg" alt="assembly_real_7" width="290" height="163" /></a></div></td>
<td><div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_8.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_8-580x326.jpg" alt="assembly_real_8" width="290" height="163" /></a></div></td>
</tr>
</tbody>
</table>
El último paso consiste en lubricar el engranaje del rotor con grasa de litio y colocar la pieza de fijación del rotor de modo que no se mueva en caso de volcar el hexágono.

<div style="text-align: center"><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_9.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_9-580x326.jpg" alt="assembly_real_9" width="580" height="326" /></a><a href="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_10.jpg"><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_10-580x326.jpg" alt="assembly_real_10" width="580" height="326" /><img src="/assets/2015-04-06-construyendo-un-zootropo-3d/assembly_real_11-580x326.jpg" alt="assembly_real_11" width="580" height="326" /></a></div>

## Resultados finales
Ha sido muy divertido diseñar un zoótropo moderno y verlo funcionar. A partir de aquí lo que queda es mostrar las imágenes con el resultado del proyecto.