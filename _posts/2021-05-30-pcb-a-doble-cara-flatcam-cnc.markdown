---
layout: post
title:  "PCB a Doble Cara con FlatCAM & CNC: Tutorial completo"
date:   2021-05-30
categories: electronica
excerpt_separator: <!--more-->
# Low quality images in /assets/2021-02-12-cnc-1610-upgrade/low (https://bulkresizephotos.com/)
---

<a href="/assets/2021-05-30-pcb-a-doble-cara-flatcam-cnc/main.jpg" >
<img 
  align="left" 
  src="/assets/2021-05-30-pcb-a-doble-cara-flatcam-cnc/low/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

 
En el video que hoy publico presento el primer tutorial de una serie sobre la producción de PCBs con máquinas CNC de bajo coste. Vamos a abordar los problemas más comunes al enfrentarnos a esta técnica construyendo una PCB a doble cara y analizando cada paso de forma detallada. 

Algunos de los temas principales que trataremos incluyen, entre otros, consejos para el correcto alineamiento de las herramientas, una explicación detallada de los parámetros de configuración de FlatCAM y una técnica de calibración especialmente diseñada para placas de doble cara.  


<!--more-->

### Parte II: PCB a Doble Cara con FlatCAM y Candle

A continuación puedes encontrar segundo video de la serie. 

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/rDLayMgCDao" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Recopilación de parámetros comunes

Aquí os dejo una recopilación de los parámetros utilizados en el video que suelo utilizar como referencia siempre que fabrico una PCB:

* FlatCAM: Herramienta de Limpieza de Cobre (Non Copper Clearing)
    <pre>
    Offset:  60%
    Method:  Standard
    Margin:  0
    Connect: 🗸
    Contour: 🗸
    Offset:  ⨯
    </pre>

* FlatCAM: Geometría 2D -> 3D G-Code
    <pre>
    Cut Z:          -0.1 (mm)
    Multi-Depth:    ⨯
    Travel Z:       1    (mm)
    Feedrate X-Y:   120  (mm/s)
    Feedrate Z:     25   (mm/s)
    Spindle Speed:  1000 (*)
    </pre>
    *** NOTA**: La velocidad de giro depende de cada máquina CNC. Típicamente vienen configuradas para que su velocidad de rotación máxima coincida con el valor 1000 aunque se puede comprobar inspeccionando el valor del parámetro `$30` (Puedes ver los valores de cada parámetro ejecutando la instrucción `$$`). 

### Software para alineamiento de doble cara

<a href="/assets/2021-05-30-pcb-a-doble-cara-flatcam-cnc/gcodeutils.jpg" >
<img 
  align="left" 
  src="/assets/2021-05-30-pcb-a-doble-cara-flatcam-cnc/low/gcodeutils.jpg" 
  alt="Main" 
  width="280"
/>
</a>

En el video utilizo un software para calibrar la cara inferior tras la rotación de la PCB utilizando unos taladros de alineamiento realizados en la cara superior. 

El software es bastante sencillo y permite recalibrar la placa corrigiendo los errores producidos durante su manipulación al girarla y recolocarla simplemente inspeccionando las nuevas posiciones de los taladros de alineamiento. 

<br/>

Puedes encontrar las instrucciones de uso y los binarios para su ejecución en los siguientes enlaces:

* [Página principal del proyecto](https://github.com/alvarogimenez/g-code-utils)
* [Instalación y ejecutables](https://github.com/alvarogimenez/g-code-utils/releases/tag/v1.0.0)