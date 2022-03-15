---
layout: post
title:  "DIY PCB: Acabado profesional con CNC + Láser"
date:   2022-03-15
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2022-03-15-diy-pcb-cnc-laser/main.jpg" >
<img 
  align="left" 
  src="/assets/2022-03-15-diy-pcb-cnc-laser/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

 En este video veremos el proceso completo para fabricar una PCB con acabado profesional utlizando una máquina CNC y un módulo láser de potencia media. Veremos la unión de las técnicas utilizadas en los videos anteriores y algunos consejos y trucos adicionales para fabricar una PCB con un acabado increíble. 

 En este artículo he recopilado los recursos utilizados durante el video así como las preguntas más frecuentes que pueden surgir durante el proceso. Además encontrarás aquí todos los parámetros de configuración de FlatCAM para conseguir los resultados del video.

<!--more-->

### Parte V: Resumen del proceso completo

A continuación puedes encontrar el quinto video de la serie. 

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/BzXxSgVrBUc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Preguntas Frecuentes

* **¿Puedo conseguir los mismos resultados con una CNC 3018?**

Sí, la CNC 3018 tiene una precisión suficiente para conseguir estos resultados. La única pega es el juego axial debido a la imprecisión de los ejes por holgura en la conexión tuerca - tornillo. Dado que esta máquina es algo más imprecisa intenta mantener el grosor de tus pistas en los diseños por encima de las 10 milésimas de pulgada (th) o 0.25mm. 

* **¿Puedo mecanizar el borde de la placa antes de metalizar los taladros?**

No. La electrodeposición es increíblemente sensible a la distribución de la corriente en la superficie de la placa. La corriente tiende a aumentar su intensidad en las esquinas y ángulos rectos, lo cual podría arruinar la uniformidad de la capa de cobre. Realiza únicamente los taladros antes de practicar la electrodeposición y asegúrate de que incluso el borde de cada taladro presenta aristas regulares sin protuberancias. 

* **No consigo ácido clorhídrico, ¿Podré metalizar los taladros con esta técnica?**

Con dificultad. El ácido clorhídrico evita la formación de óxidos que pueden derivar en arbolaciones en la placa durante el proceso. Si no empleas ácido clorhídrico trata de mantener una buena agitación en la cubeta (incluso introduciendo un sistema de agitación por aire). 

* **¿Puedo utilizar una fresa con el lateral plano y forma de V?**

Sí pero tienen muy mal rendimiento. Estas fresas tienen generalmente un mal equilibrado, ocasionando un aumento del diámetro efectivo de corte y la proliferación de bordes irregulares. Si te tomas el suficiente tiempo para alinear y equilibrar la broca se pueden obtener resultados decentes. Como consejo: no sobrepases los 45 mm/min de velocidad horizontal para no dañar la delicada punta de este tipo de fresas. 

* **¿Qué sucede si el mapa de aturas coincide con uno de los taladros?**

Trata de modificar los márgenes manualmente para que el punto del mapa deje de coincidir o modifica la cantidad de puntos en la matriz. 

* **¿Es necesario dar la capa de máscara blanca si no quiero máscara de componentes?**

No. La capa blanca es necesaria únicamente en caso de realizar la máscara de componentes. 

* **Después de aplicar el laser, uno de los pads se ha desprendido, ¿Qué ha sucedido?**

Esto es algo bastante común y tiene solución. El motivo de que el pad se haya desprendido es que el láser incidió sobre el margen del pad que no está recubierto de cobre. Esto puede deberse a dos causas:
1. El programa G-Code no está correctamente alineado. En este caso deberás tomarte algo más de tiempo para alinear correctamente el programa de forma que el láser incida únicamente sobre el cobre y nunca sobre la fibra de vidrio de la placa. 
2. El margen es insuficiente. En algunos casos el margen de 0.15mm es insuficiente y el láser incide en el exterior del pad dañando la fibra de vidrio. En este caso puedes aumentar el margen en FlatCAM durante la generación del programa G-Code o directamente en el programa de diseño de la PCB (Kicad, proteus, etc). 

### Composición del electrolito y corriente de electrodeposición

A continuación puedes ver la composición exacta del electrolito para cualquier cantidad base de agua:

- Agua desionizada
- 250g/L de Sulfato de cobre pentahidratado (CuSO4·5H2O)
- 190g/L de Ácido Cítrico anhídro (C6H8O7)
- 0.15mL/L de Ácido Clorhídrico (HCl) al 20% (~3 gotas)
- 5mL/L de Polisorbato 20 (Opcional)

La corriente debe ser de 21.5mA/cm2 (~20ASF) y debe calcularse en base al área de cobre que queremos revestir. **Recuerda multiplicar por dos en caso de las placas a doble cara**. Con esta corriente y un tiempo de 40 minutos, deberíamos obtener una deposición de unas 20 micras. 

### Configuración de FlatCAM

#### Programa de taladrado de la placa

<pre>
    Cut Z:          -3   (mm)
    Multi-Depth:    ⨯
    Travel Z:       1    (mm)
    Feedrate Z:     25   (mm/s)
    Spindle Speed:  1000 (*)
</pre>
_* NOTA: La máxima velocidad de giro de la máquina puede consultarse en la variable `$30` (Ejecuta el comando `$$`para inspeccionar el valor de todas las variables)_ 

#### Programa de mecanizado de las caras superior e inferior

<pre>
    Overlap: 75% 
    Method:  Standard
    Margin:  0
    Connect: 🗸
    Contour: 🗸
    Offset:  ⨯
</pre>

<pre>
    Cut Z:          -0.1 (mm)
    Multi-Depth:    ⨯
    Travel Z:       1    (mm)
    Feedrate X-Y:   120  (mm/s)
    Feedrate Z:     25   (mm/s)
    Spindle Speed:  1000 (*)
</pre>

_* NOTA: La máxima velocidad de giro de la máquina puede consultarse en la variable `$30` (Ejecuta el comando `$$`para inspeccionar el valor de todas las variables)_ 

#### Soldermask

<pre>
    Tool Width: 0.15mm
    Overlap:    80% 
    Offset:     0.15mm
    Method:     Standard
    Connect:    🗸
    Contour:    🗸
</pre>

<pre>
    Preprocessor:   GRBL_Laser
    Feedrate X-Y:   1000  (mm/s)
    Laser Power:    250   (*)
</pre>

_* NOTA: La potencia para eliminar la máscara y desvelar completamente el cobre depende de cada láser. Recuerda ejecutar una prueba de potencia para averiguar qué potencia es adecuada en tu láser._ 

#### Silkscreen

<pre>
    Tool Width: 0.15mm
    Overlap:    0% 
    Offset:     0
    Method:     Standard
    Connect:    ⨯
    Contour:    🗸
</pre>

<pre>
    Preprocessor:   GRBL_Laser
    Feedrate X-Y:   1000  (mm/s)
    Laser Power:    100   (*)
</pre>

_* NOTA: La potencia para eliminar únicamente la primera capa de máscara depende de cada láser. Recuerda ejecutar una prueba de potencia para averiguar qué potencia es adecuada en tu láser._ 

### Recursos adicionales

A continuación dejo los modelos 3D utilizados en este tutorial:

<table class="center">
    <tr>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Electroplating_Support.png">
                <img 
                src="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Electroplating_Support.png" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Electroplating_Support.stl">PCB_Electroplating_Support.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Long.png">
                <img 
                src="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Long.png" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Long.stl">PCB_Support_Long.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Short.png">
                <img 
                src="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Short.png" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Short.stl">PCB_Support_Short.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Nut.png">
                <img 
                src="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Nut.png" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2022-03-15-diy-pcb-cnc-laser/PCB_Support_Nut.stl">PCB_Support_Nut.stl</a>
        </td>
    </tr>
</table>
