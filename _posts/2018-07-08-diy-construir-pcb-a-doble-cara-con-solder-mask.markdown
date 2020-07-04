---
layout: post
title:  "DIY: Construir PCB a doble cara con Solder Mask"
date:   2018-07-08 00:01:35 +0200
categories: electronica
excerpt_separator: <!--more-->
---
<img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/PCB_Portada.jpg" alt="PCB_Portada" width="280" height="201" />
Poder realizar Placas de Circuito Impreso con acabados semiprofesionales es una buena forma de aproximar el prototipado a la realidad de la producción de un proyecto.

Realizar prototipos utilizando placas de ensayo tipo ProtoBoard o placas preperforadas aleja de la realidad el prototipo y puede conllevar problemas durante su paso a producción. Además, una vez depurada la técnica de diseño y construcción de PCB de forma casera, es posible obtener más rápido este tipo de placas que las de tipo prototipo sobre soportes perforados. Hace bastantes años comencé a desarrollar técnicas para construir PCB sin necesidad de recurrir a servicios de terceros y, no sin esfuerzo, he conseguido extraer una lista de pasos a seguir y algunos trucos que hoy quisiera compartir aquí. En la entrada de hoy veremos como construir una PCB a doble cara, combinando componentes <em>Through Hole</em> y SMD empleando un acabado de Máscara Antisoldante (o <em>Solder Mask</em>).

<!--more-->

Se puede obtener mucha documentación sobre construcción de PCB en internet y no tendría sentido repetir el trabajo que ya otras muchas personas han realizado documentando el proceso básico de construcción de una placa de circuitos. Me gustaría centrarme en todos los problemas que he encontrado durante mi aprendizaje y en los trucos que utilizo habitualmente para solucionarlos. Comencemos por el principio: el diseño de la placa.
## Diseño
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_00.png"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_00-580x431.png" alt="Design_00" width="280" height="208" /></a>Existen varias <em>suites</em> de <em>software </em>de diseño para PCB. En mi caso he utilizado siempre la <em>suite</em> de <em>Proteus </em>pero el lector puede utilizar la que más le convenga.

<em>Proteus</em> ofrece dos entornos: <em>Ares</em> e <em>Isis, </em>utilizados para el diseño de PCB y esquemas electrónicos respectivamente. Lleva un tiempo familizarse con este tipo de entornos de desarrollo y, como dije antes, queda fuera del objetivo principal de esta entrada documentar aquellos procesos que ya están sobradamente documentados en internet.

De cara a ilustrar el proceso de creación de PCB vamos a utilizar una placa que estoy diseñando para un proyecto actual. La placa consta de dos caras y utiliza componentes <em>Through Hole</em> y SMD por lo que es un ejemplo perfecto para este tutorial. He aquí un vistazo rápido del diseño de la placa en <em>Ares.</em>

<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_01.png"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_01-580x518.png" alt="Design_01" width="250" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_02.png"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_02-580x518.png" alt="Design_02" width="250" /></a></td>
</tr>
</tbody>
</table>

Cada placa requiere una configuración distinta así que es complicado extraer recetas para este proceso. Sin embargo, siempre intento seguir algunas recomendaciones de cara a evitar lamentos durante la fase de atacado:
<ul>
	<li><strong>Utiliza pistas con un grosor adecuado</strong>. Las pistas con un grosor excesivamente fino pueden acabar desapareciendo si el fotolito se separa levemente en alguna zona de la placa durante la insolación (Algo que veremos que es posible más adelante). Suelo utilizar, si la placa lo permite, pistas de 0.5mm de grosor (o 20th en el equivalente en pulgadas).</li>
	<li><strong>Aumenta el tamaño de los </strong><em><strong>pads.</strong> </em>Los <em>pads</em> que vienen por defecto en algunos componentes son demasiado pequeños y puede que, tras realizar los taladros, quede demasiada poca superficie de cobre para soldar.</li>
	<li><strong>Realiza <em>Copper Pour</em> </strong>en todas las placas. En <em>Ares</em> esta funcionalidad se genera utilizando el modo <i>Zone. </i>El objetivo es crear zonas de cobre en todas las partes de la placa donde no exista trazado. De esta forma evitarás que el ácido deba atacar demasiado cobre durante el atacado consiguiendo mejores tiempos de atacado y evitando la posibilidad de que la reacción química del atacador (En caso de utilizar un atacador rápido) se acabe antes de terminar la placa entera o comience a consumir las pistas con fatales resultados. Aquí una placa con y sin relleno de cobre:
<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_CopperPour.png" ><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_CopperPour-580x308.png" alt="Design_CopperPour" width="450" height="239" /></a>
</div>
</li>
</ul>
<ul>
	<li><strong>Vigila el espacio</strong> entre la zona de <em>Copper Pour </em>y las pistas. Al menos suelo dejar 0.5mm de espacio para evitar que se generen puentes entre las pistas y el relleno de cobre (normalmente ligado a alguna red común como GND).</li>
</ul>
Suelo intentar también mantener el máximo realismo posible en la visualización 3D de las placas. La visualización renderizada de una PCB puede ayudar a descubrir problemas de diseño como colisiones entre componentes o falta de espacio entre algunos elementos. Esta es la visualización 3D de las placas con las que vamos a trabajar en esta entrada.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_03.png"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_03-580x434.png" alt="Design_03" width="450" height="337" /></a> <a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_04.png"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_04-580x434.png" alt="Design_04" width="450" height="337" /></a>
</div>

&nbsp;

Algunos de los componentes que hay en esta placa no existen en la representación por defecto de <em>Ares. </em>Normalmente suelo diseñarlos utilizando <em>Autodesk Inventor</em> y sustituyo la representación original por el diseño. Como ejemplo, esta placa utiliza potenciómetros deslizantes de <em>Bourns</em> de tipo PTA4543. Este es el diseño que he hecho rápidamente en <em>Inventor.</em>

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_PTA4543.png"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_PTA4543-580x323.png" alt="Design_PTA4543" width="580" height="323" /></a>
</div>

La diferencia entre utilizar las representaciones por defecto que ofrece <em>Ares</em> para este componente y el diseño rápido que he realizado del PTA se muestran en la siguiente imagen:

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_PTA_diff.png"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_PTA_diff-580x246.png" alt="Design_PTA_diff" width="580" height="246" /></a>
</div>

Animo al lector a que experimente con <em>Autodesk Inventor </em>o cualquier otro programa de diseño métrico de cara a mejorar la experiencia de diseño de las PCB. De no haber sido por utilizar esta técnica me habría encontrado con más de un problema de diseño.

## Insolación y Revelado
Una vez diseñada la placa comenzaremos con la primera fase de la construcción fuera del ordenador: la insolación. Las placas de circuitos hechas de fibra y una lámina de cobre, se pueden adquirir con un barniz protector sensible a la luz ultravioleta. Normalmente se utilizan placas de fibra positivas que preservarán el barniz protector en aquellas zonas que no hayan sido expuestas a la luz UV y perderán la protección en aquellas zonas que si lo hayan sido. Para esta etapa necesitaremos lo siguiente:
<ul>
	<li><strong>Una insoladora</strong>. Aquí comienza la lucha entre los procedimientos puramente caseros y la adquisición de materiales semiprofesionales. En el comienzo de mi experiencia fabricando placas de circuitos utilicé todo tipo de técnicas caseras: una lámpara halógena, exponer la placa utilizando luz solar, etc. Pronto me di cuenta de que adquirir una insoladora era la mejor opción y se ha convertido en una herramienta indispensable en mi taller. Mi insoladora, una IF-48, está formada por cuatro tubos de luz actínica ultravioleta de 8W en una sola cara y cuesta menos de 100€.
	<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_if48.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_if48-580x404.jpg" alt="Insolacion_if48" width="450" height="313" /></a>
</div>
</li>
	<li><strong>Revelador comercial de Hidróxido de Sodio. </strong>Nuevamente sostengo que utilizar técnicas caseras reduce mucho la capacidad de reproducción de un proyecto. Siempre utilizo revelador comercial a base de Hidróxido de Sodio fácilmente adquirible en cualquier tienda de electrónica por menos de 5€.</li>
	<li><strong>Láminas de papel vegetal.</strong> En este punto existen dos opciones a elegir: hojas de transparencia o papel vegetal. Mucha gente utiliza hojas de transparencia pero no se llevan nada bien con las impresoras de chorro de tinta. Siempre he obtenido muy buenos resultados con el papel vegetal y funciona tanto con impresoras de chorro de tinta como con impresoras láser así que es mi preferencia. Utilizo hojas de papel vegetal con una densidad de 95 gramos por metro cuadrado.</li>
	<li><strong>Cristales, pinzas, pegamento...<em> </em></strong>Necesitaremos al menos dos cristales que se pueden obtener fácilmente comprando marcos de fotos baratos y, al menos, cuatro pinzas de oficina. Pegamento de <em>cianocrilato</em> con pincel es de agradecer también en esta etapa del proceso.</li>
</ul>
Comenzaremos imprimiendo los fotolitos en el papel vegetal haciendo al menos dos copias de cada cara que luego sobrepondremos para conseguir mayor opacidad. Recomiendo configurar la impresora para utilizar el mayor volumen de tinta posible. Os dejo algunas fotos de este proceso:
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_01-580x326.jpg" alt="Insolacion_fotolito_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_02-580x326.jpg" alt="Insolacion_fotolito_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Una vez terminados los fotolitos de las dos capas superior e inferior utilizando dos láminas de papel vegetal para cada uno debemos superponer ambos fotolitos alineando los patrones con cuidado. Cuando los tengamos alineados pegaremos tan solo uno de los extremos formando una especie de <em>librito</em> cuya portada y contraportada son los fotolitos de ambas capas. Nos podemos ayudar de una lámpara para mirar a través de los fotolitos y comprobar si efectivamente están alineados antes de pegarlos.
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_03.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_03-580x326.jpg" alt="Insolacion_fotolito_03" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_04.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_fotolito_04-580x326.jpg" alt="Insolacion_fotolito_04" width="300" /></a></td>
</tr>
</tbody>
</table>
El siguiente paso es cortar la placa y situarla dentro del fotolito. Suelo utilizar un patrón impreso en papel con el tamaño real de la placa para realizar el corte y, una vez conseguido el tamaño final de la placa, utilizo dos cristales de tamaño no muy superior a la placa para prensarla por ambos lados. Es importante que los cristales no sean de un tamaño muy superior a la placa si no son muy gruesos porque, de lo contrario, tenderían a combarse y el fotolito quedaría separado de la placa.
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_01-580x326.jpg" alt="Insolacion_corte_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_02-580x326.jpg" alt="Insolacion_corte_02" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_03.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_03-580x326.jpg" alt="Insolacion_corte_03" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_04.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_corte_04-580x326.jpg" alt="Insolacion_corte_04" width="300" /></a></td>
</tr>
</tbody>
</table>
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_luz.jpg"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_luz-580x389.jpg" alt="insolacion_luz" width="280" height="188" /></a>
La insolación es el primer proceso crítico de la construcción de PCB y requiere cierta experiencia previa y un poco de experimentación en cada caso. Es absolutamente imposible poner una cifra al tiempo de insolación ya que depende de múltiples factores. En primer lugar en función de la potencia de la insoladora que tengamos será necesario más o menos tiempo de insolación. En segundo lugar, por cada tipo de placa, es decir, por cada fabricante, es posible que cambien los tiempos de exposición. En tercer lugar la opacidad del fotolito influye de forma crítica en el tiempo de exposición.

Por estos motivos recomiendo experimentar con los tiempos de exposición comprando una placa positiva, cortándola en trozos pequeños, de 2cm de lado quizá, y realizando pruebas de exposición entre los 2 y lo 10 minutos. Para cada configuración de fabricante de placa, tipo de fotolito e insoladora obtendremos un tiempo adecuado de exposición descartando las placas que no se revelen debido a un tiempo escaso de exposición y aquellas que presenten desgaste o desaparición completa de los trazos que deberían quedar protegidos debido a un tiempo excesivo de exposición. En mi caso, con mi insoladora, papel vegetal y el tipo de placas que suelo comprar utilizo un tiempo de exposición de 7 minutos.

Una vez insolada la placa deberemos preparar la disolución de Hidróxido de Sodio en una cubeta o recipiente similar y revelar la placa. El tiempo de revelado no debería ser crítico si la exposición ha sido correcta. Deberíamos ver como desaparece el barniz de las zonas que han sido expuestas dejando el dibujo en positivo de las pistas de la placa mientras agitamos levemente el recipiente con el revelador.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_proceso_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_proceso_01-580x326.jpg" alt="Insolacion_proceso_01" width="580" height="326" /></a> <a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_proceso_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_proceso_02-580x326.jpg" alt="Insolacion_proceso_02" width="580" height="326" /></a>
</div>

Si los trazos de las pistas no aparecieran o algunas de las pistas aparecieran borradas deberíamos repetir el proceso de insolación con una nueva placa cambiando el tiempo de exposición según corresponda. Tras revelar la placa este es el resultado donde se puede observar el cobre desprotegido en las zonas sobre las que actuará el ácido más adelante:
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_resultado_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_resultado_01-580x416.jpg" alt="Insolacion_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_resultado_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_resultado_02-580x416.jpg" alt="Insolacion_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Algunas anotaciones sobre el proceso de insolación:
<ul>
	<li>Es posible que algunas <strong>pistas queden borrosas</strong>. Esto es debido a múltiples factores entre los que se encuentran que el grosor del fotolito sea demasiado grande (Por ejemplo utilizando dos transparencias en lugar de papel vegetal que es más delgado) o que el fotolito se separe de la placa durante la insolación por no quedar debidamente prensadas entre los cristales.</li>
	<li>Tras la insolación aconsejo<strong> revisar la placa en busca de defectos</strong>. Si dos pistas aparecieran unidas o hubiera puentes entre las pistas y el relleno de cobre debido a las imprecisiones que he comentado anteriormente existe la posibilidad de corregirlo utilizando alguna herramienta de corte. Se puede raspar la superficie y eliminar el barniz protector de aquellas zonas donde no deba estar antes del atacado.</li>
	<li>Hay que tener especial cuidado al revelar las placas a doble cara cuando se agita la cubeta porque el lado que queda en la parte inferior<strong> podría arañarse</strong> con el roce. Si se araña alguna placa podría quedar cortada y habría que repararla en una etapa posterior.</li>
</ul>

## Atacado
Si el resultado de la etapa anterior ha sido exitoso el atacado químico de la placa no debería ser problemático. Los barnices que vienen en las placas de fibra positivas suelen ser altamente resistentes al ácido y dan un amplio margen de tiempo para realizar el atacado. Para esta fase necesitaremos lo siguiente:
<ul>
	<li><strong>Juego de atacador rápido comercial</strong> a base de Ácido Clorhídrico y Perborato Sódico. Nuevamente reitero mi posición frente a utilizar soluciones caseras de químicos para la construcción de PCB. Considero que utilizar soluciones comerciales hace que el proceso sea fácilmente repetible sin variar las condiciones y los tiempos de cada etapa. Además con el paso del tiempo me he dado cuenta de que el ahorro que supone utilizar químicos caseros frente a las soluciones comerciales es realmente bajo si tenemos en cuenta el porcentaje habitual de fracaso utilizando soluciones caseras.</li>
	<li><strong>Protección para las manos y cara.</strong> Es importante utilizar protección para las manos ya que tarde o temprano entrarán en contacto con el ácido mientras atacamos la placa. No se muere nadie por tocar el ácido pero no es nada bueno para la piel si lo utilizamos habitualmente (por no hablar de si tenemos alguna herida abierta). También aconsejo utilizar mascarilla y protección para los ojos por si las salpicaduras.</li>
</ul>
Es un poco complicado hacer fotos teniendo los guantes puestos así que tengo apenas un par de fotos de este proceso. El tiempo de atacado depende del tamaño de la placa y de la cantidad de cobre que el ácido deba atacar (Aquí cobra importancia utilizar relleno de cobre durante la fase de diseño). Normalmente suele durar entre 5 y 10 minutos.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_01-580x326.jpg" alt="Atacado_01" width="580" /></a><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_02.jpg">
<img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_02-580x326.jpg" alt="Atacado_02" width="580" /></a>
</div>

Nada más introducir la placa en la solución deberíamos ver como se oscurecen las zonas de cobre descubiertas y el ácido debería adquirir un color verdoso como se aprecia en la imagen anterior. El cobre irá desapareciendo gradualmente mientras agitamos, con no mucho ímpetu,  la cubeta. Podemos sacar periódicamente la placa para darle la vuelta y para comprobar qué cantidad de cobre sin barniz queda por consumir.
<table>
<tbody>
<tr>
<td>
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_01-580x416.jpg" alt="Atacado_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_02-580x416.jpg" alt="Atacado_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Una vez veamos que no queda ninguna parte de cobre que deba ser atacado podemos limpiar el barniz restante utilizando acetona. También es el momento de realizar la primera comprobación sobre la integridad de las pistas utilizando alguna luz de fondo.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_final_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_final_02-580x326.jpg" alt="Atacado_final_02" width="580" height="326" /></a> <a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_final_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_final_01-580x326.jpg" alt="Atacado_final_01" width="580" height="326" /></a>
</div>

Algunas anotaciones sobre el proceso de atacado:
<ul>
	<li>Tener cuidado al agitar la cubeta para<strong> no dañar el barniz.</strong> Igual que tuvimos cuidado mientras revelábamos la placa para no dañar el barniz de la parte que quedaba contra la cubeta durante el proceso hay que prestar especial atención mientras aplicamos el ácido. El ácido tenderá a eliminar parte del barniz y a hacerlo más vulnerable a arañazos. Debemos agitar con cuidado la cubeta y asegurarnos de que es perfectamente lisa ya que algún residuo sólido adherido de atacados anteriores podría dañar el barniz.</li>
	<li><strong>No hay que ser impaciente</strong> durante los primeros minutos del atacado. Es posible que tarde varios minutos en comenzar a desaparecer el cobre de la placa, es algo normal.</li>
	<li>Si alguna de las pistas hubiera resultado dañada puede <strong>estañarse</strong>. Cualquier arañazo sobre el barniz provocará que alguna pista quede interrumpida. Por eso es importante observar con detenimiento la placa al trasluz en busca de pistas interrumpidas. Con la ayuda de un soldador y estaño podemos crear un puente para reparar la pista.</li>
</ul>
## Solder Mask

<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Portada.jpg"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Portada-580x475.jpg" alt="SolderMask_Portada" width="350" height="287" /></a>

Si queremos hacer placas que utilicemos durante años es necesario aplicarles máscara antisoldante. Esta máscara protegerá al cobre del óxido durante los años y, además, facilitará enormemente el soldado posterior de la placa.

Existen varias formas de aplicar la máscara antisoldante: utilizando métodos de serigrafía, utilizando láminas adhesivas por calor sensibles a UV o atacables químicamente y utilizando resinas sensibles a la luz ultravioleta. Utilizaremos esta última técnica para darle un aspecto profesional a nuestra placa en esta entrada. Necesitaremos los siguientes materiales:
<ul>
	<li><strong>Resina curable por luz Ultravioleta</strong>. Estas resinas son baratas y fáciles de obtener por internet. Se curan utilizando luz ultravioleta lo cual nos permite utilizar las técnicas que ya usamos durante la insolación con los mismos conceptos. Yo utilizo la que aparece en la siguiente imagen:
	<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resina_uv.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resina_uv-580x326.jpg" alt="SolderMask_resina_uv" width="450" height="253" /></a>
</div>
	</li>
	<li>Un sistema para <strong>alzar la placa</strong> durante el alineamiento. Se puede montar un pequeño sistema de alzado para sostener el cristal que nos permita introducir una luz potente debajo (yo utilizo el modo linterna del teléfono). Esto nos permitirá alinear el fotolito a la placa con mayor facilidad.
<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_banco_trabajo.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_banco_trabajo-580x326.jpg" alt="SolderMask_banco_trabajo" width="450" height="253" /></a>
</div></li>
	<li><strong>Láminas de polipropileno transparente.</strong> Aquí está la clave para utilizar este tipo de resinas que puede traer muchos quebraderos de cabeza. Se pueden ver muchos tutoriales y videos en internet sobre la aplicación de este tipo de resina en la que se utiliza una hoja transparencia para esparcir uniformemente el producto. El problema es que estas resinas se adhieren al nylon, acetato, poliéster, PVC y derivados, que es el material con el que está construida la práctica totalidad de hojas de transparencia. He aprendido que para una experiencia agradable con estas resinas hay que utilizar láminas de polipropileno o polietileno.</li>
</ul>
El primer paso, igual que en la etapa de insolado, es imprimir los fotolitos en papel vegetal. Recomiendo utilizar un par de capas de papel vegetal por cada cara para hacer menos crítico el tiempo de exposición a la resina.
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Resist_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Resist_01-580x326.jpg" alt="SolderMask_Resist_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Resist_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_Resist_02-580x326.jpg" alt="SolderMask_Resist_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Situaremos un cristal en la base que hemos preparado y sobre él situaremos la placa. Recomiendo poner en la base un trozo de transparencia (aquí sí da igual el material de la transparencia) para que el cristal no se manche durante la aplicación de la resina. Aplicaremos la resina en la placa y situaremos una lámina de polipropileno encima que nos ayudará a extenderla uniformemente con la ayuda de una tarjeta de crédito o similar. Una vez extendida la resina situaremos el fotolito de papel vegetal sobre la lámina de polipropileno y la alinearemos con ayuda de una luz de fondo. Tras estar conformes con el alineado fijaremos todo el conjunto con otro cristal y unas pinzas, del mismo modo que lo hicimos durante la insolación de la placa.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_01-580x326.jpg" alt="SolderMask_proceso_01" width="580" height="326" /></a> 
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_02-580x326.jpg" alt="SolderMask_proceso_02" width="580" height="326" /></a>
</div>

Nuevamente el proceso de exposición de la resina a la luz ultravioleta requiere experimentar con los tiempos. Cada tipo de resina, opacidad de fotolito e insoladora dará como resultado tiempos distintos. Cuando mayor sea la opacidad de los <em>pads</em> del fotolito, sin embargo, se reduce el componente crítico del tiempo de exposición. Es por eso que utilizo dos láminas de papel vegetal en lugar de una.

Recomiendo cortar pequeños trozos de placa de cobre virgen y experimentar con los tiempos de exposición hasta lograr el adecuado. Demasiado poco tiempo y la resina no se curará quedando líquida. Demasiado tiempo y se curarán los pads haciendo imposible retirarlos de forma cómoda. En mi caso el tiempo de exposición óptimo es de 10 minutos.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_03.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_03-580x326.jpg" alt="SolderMask_proceso_03" width="580" height="326" /></a> 
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_04.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_proceso_04-580x326.jpg" alt="SolderMask_proceso_04" width="580" height="326" /></a>
</div>

Tras finalizar al exposición la lámina de polipropileno debería desprenderse con facilidad de la placa. En caso de utilizar otro material puede que la resina quede adherida a la lámina haciendo que retirarla sea prácticamente imposible sin romper el patrón. Los <em>pads</em> deberían seguir conteniendo la resina líquida que debería poder retirarse fácilmente con un algodón o trozo de papel suave.

Tras repetir el proceso para ambas caras este ha sido el resultado obtenido:
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_01-580x416.jpg" alt="SolderMask_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_02-580x416.jpg" alt="SolderMask_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Algunas anotaciones sobre la aplicación de la máscara antisoldante:
<ul>
	<li>Es importante que los <em>pads</em> tengan la <strong>mayor opacidad posible</strong>. Esto reduce mucho la incertidumbre sobre el tiempo de exposición.</li>
	<li><strong>Trata de extender uniformemente la resina</strong>. Es importante que no queden zonas demasiado oscuras, lo cual significa que hay demasiada resina acumulada, porque eso implicará que no se curen adecuadamente y se pueden desprender al retirar la lámina de polipropileno.</li>
	<li><strong>Si sale mal no está todo perdido.</strong> No hay que volver a empezar con una placa nueva, es posible retirar la resina lijando toda la superficie. Desgraciadamente no conozco ningún método químico para retirar la resina pero el cobre es agradecido para el lijado y pulido.</li>
</ul>
## Taladro
Esta parte del proceso no debería tener mucha complicación. Utilizo un juego de brocas desde los 0.6 mm a los 3 mm y varío el grosor en función de la necesidad del componente. En este caso concreto utilizaré 0.7 mm para las vías, los CI y los conectores tipo codo, 1 mm para los conectores de los PTA, 1.5 mm para los anclajes de los PTA y 2.5 mm para los agujeros de fijación de la placa.

<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_01-580x326.jpg" alt="Taladro_01" width="580" height="326" /></a> <a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_02-580x326.jpg" alt="Taladro_02" width="580" height="326" /></a>
</div>

Recomiendo utilizar una hoja de cualquier material para poner debajo de la placa mientras la movemos para taladrarla dado que al estar deslizando la placa continuamente sobre la superficie podría arañarse. Tras realizar todos los taladros de esta placa este sería el resultado:

<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_01-580x416.jpg" alt="Taladro_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_02-580x416.jpg" alt="Taladro_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>

Aconsejo adquirir un taladro de columna para mejorar la precisión de los taladros. Estuve muchos años taladrando "a pulso" y eso impacta directamente en la calidad de los taladros. Además, dado el pequeño diámetro de las brocas que se utiliza para taladrar las placas, es más frecuente la rotura de las brocas si no se utiliza un taladro de columna y algunas no son precisamente baratas. El taladro de columna que yo tengo no costó más de 100€ así que es un precio asequible.
## Soldadura
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_portada.jpg"><img align="left" src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_portada-580x399.jpg" alt="Soldadura_portada" width="350" height="241" /></a>

Sin duda esta es la parte más divertida de todo el proceso. Hay que disfrutarla antes de terminarlo todo y comprobar que <del>nada funciona</del> todo funciona a la perfección, así que manos a la obra.

Comenzaremos preparando todos los componentes que vamos a utilizar para la placa como se muestra en la imagen de la izquierda y revisando los esquemáticos para asegurar el lugar de destino de cada componente. Si bien no existe un orden establecido para soldar los componentes resulta obvio que hay que planificarlos en función de cuánto vayan a estorbarse los unos a los otros durante la soldadura. Yo suelo seguir el orden que os presento a continuación:
<ol>
	<li>Soldadura de los componentes más pequeños tipo SMD. Para soldar estos componentes la máscara antisoldante ayuda bastante. Como ayuda adicional suelo utilizar una cantidad muy pequeña de pegamento de cianocrilato para fijar temporalmente los componentes a la placa y que no se muevan durante la soldadura.</li>
	<div style="text-align: center">
	<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_01-580x326.jpg" alt="Soldadura_proceso_01" width="400" height="225" /></a> 
	<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_02-580x326.jpg" alt="Soldadura_proceso_02" width="400" height="225" /></a>
	</div>

	<li>Soldadura de las vías. Creo que queda fuera del ámbito de la construcción de PCB caseras las vías obtenidas por procesos electro-químicos en ámbitos profesionales. Para crear las vías utilizo trozos de alambre de cobre soldados a ambos lados como se muestra a continuación:
	<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_03.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_03-580x326.jpg" alt="Soldadura_proceso_03" width="400" height="225" /></a> 
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_04.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_04-580x326.jpg" alt="Soldadura_proceso_04" width="400" height="225" /></a> 
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_05.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_05-580x326.jpg" alt="Soldadura_proceso_05" width="400" height="225" /></a> 
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_06.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_06-580x326.jpg" alt="Soldadura_proceso_06" width="400" height="225" /></a>
</div>
</li>
	<li>Soldadura de los componentes de menos a mayor altura. De esta forma la placa no cojeará al apoyarla para soldar el resto de componentes.
	<div style="text-align: center">
<a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_07.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_07-580x326.jpg" alt="Soldadura_proceso_07" width="400" height="225" /></a> <a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_08.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_proceso_08-580x326.jpg" alt="Soldadura_proceso_08" width="400" height="225" /></a>
</div></li>
</ol>
El resultado obtenido después de realizar la soldadura es el siguiente:
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_01-580x416.jpg" alt="Soldadura_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_02-580x416.jpg" alt="Soldadura_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>
Algunas anotaciones sobre el proceso de soldadura:
<ul>
	<li><strong>Calentar la pata del componente</strong> al soldar. Mientras soldamos debemos calentar la pata del componente con la finalidad de que sea esta la que funda el estaño, esto generará una soldadura mucho más resistente.</li>
	<li>Cuidado con las <strong>soldaduras falsas.</strong> No calentar la pata del componente como se explica en el punto anterior o la presencia de residuos en el estaño o la punta del soldador puede provocar soldaduras falsas. Las soldaduras falsas tienen aspecto de soldadura normal pero no existe una buena conexión con la pista o la pata del componente.</li>
	<li><strong>Vigila la temperatura de los integrados</strong>. La mayoría de los circuitos integrados soportan bastante temperatura momentánea de cara a realizar la soldadura pero se ha de tener especial cuidado en circuitos integrados con muchas patas ya que pueden llegar a calentarse demasiado y dañar así el componente. Si es posible alterna entre diferentes componentes mientras sueldas este tipo de integrados.</li>
</ul>
## Conclusiones
Me ha llevado muchos años pulir la técnica de construcción de placas de circuito impreso. Decenas de ellas se han ido a la basura por todos y cada uno de los puntos que he comentado en las anotaciones de cada paso. Mi intención con esta entrada es ahorrar a futuros iniciados en el mundo de la construcción de PCB todos los errores que yo cometí durante años y que me han servido para aprender y perfeccionar la técnica hasta llegar a los resultados que he expuesto aquí.

A modo de resumen os dejo la comparativa del resultado de cada etapa del proceso y espero comentarios con nuevas ideas o mejoras sobre mi técnica de construcción casera de placas de circuito impreso.
<table>
<tbody>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_05.png"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_05-580x376.png" alt="Design_05" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_06.png"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Design_06-580x376.png" alt="Design_06" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_resultado_01-580x416.jpg" alt="Insolacion_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Insolacion_resultado_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/insolacion_resultado_02-580x416.jpg" alt="Insolacion_resultado_02" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_01.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_01-580x416.jpg" alt="Atacado_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_02.jpg"><img src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Atacado_resultado_02-580x416.jpg" alt="Atacado_resultado_02" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_01-580x416.jpg" alt="SolderMask_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/SolderMask_resultado_02-580x416.jpg" alt="SolderMask_resultado_02" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_01-580x416.jpg" alt="Taladro_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Taladro_resultado_02-580x416.jpg" alt="Taladro_resultado_02" width="300" /></a></td>
</tr>
<tr>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_01.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_01-580x416.jpg" alt="Soldadura_resultado_01" width="300" /></a></td>
<td><a href="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_02.jpg"><img  src="/assets/2018-07-08-diy-construir-pcb-a-doble-cara-con-solder-mask/Soldadura_resultado_02-580x416.jpg" alt="Soldadura_resultado_02" width="300" /></a></td>
</tr>
</tbody>
</table>