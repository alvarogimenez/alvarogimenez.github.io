---
layout: post
title:  "Cómo soldar con una lata de refresco (y alguna cosa más...)"
date:   2022-06-16
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2022-06-16-como-soldar-con-una-lata-de-refresco/main.jpg" >
<img 
  align="left" 
  src="/assets/2022-06-16-como-soldar-con-una-lata-de-refresco/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

En el video que hoy publico vemos cómo fabricar una plantilla de soldadura casera con dos técnicas muy diferentes. Además para ilustrar el proceso he creado una placa de entrenamiento para un microcontrolador PIC18F2550 que puedes encontrar al final de este artículo. 

Del mismo modo que ya vimos en videos anteriores con la producción casera de placas de circuito impreso fabricar plantillas de soldadura SMD es también un proceso asequible en nuestro taller. Veremos un par de técnicas disponibles (atacado químico y meanizado CNC) y compararemos nuestros resultados con una plantilla profesional cortesía de <a href="http://www.pcbway.com">PCBWay</a>

<!--more-->

### Parte VI: Cómo fabricar una plantilla de soldadura

A continuación puedes encontrar el sexto  video de la serie. 

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/zZ8cb5VgFZY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Preguntas Frecuentes

* **No consigo que la lámina base quede completamente plana, ¿Qué puede estar sucediendo?**
Muy probablemente necesite más tiempo bajo la plancha. A veces puede ser necesario dejar la lámina hasta 30 minutos o más para que se aplane por completo. Cuanto más tiempo pase bajo la plancha, mejor será el acabado. 

* **Mi lámina se ha curvado de nuevo al extraerla de la CNC, ¿Se puede arreglar?**
Sí, simplemente vuelve a dejarla bajo la plancha el tiempo necesario. No olvides de vigilar la placa siempre que se encuentre bajo la plancha. 

* **¿Se puede utilizar el atacado químico con cualquier lata de refresco?**
Sí, pero verifica con un multímetro que la cara inferior no conduce la electricidad y que, por lo tanto, tiene un recubrimiento epoxi transparente para protegerla durante el atacado. 

* **No tengo una placa caliente, ¿Puedo utilizar una pistola de aire caliente?**
Claro. Manejar la pistola de aire caliente es algo más complicado, en mi opinión, porque algún componente se puede desplazar durante el proceso pero es una técnica ampliamente utilizada por todos los profesionales y con la que obtendrás buenos resultados.

* **¿Puedo emplear una lámina que no provenga de una lata de refresco?**
Sí pero ten cuidado con el grosor de la lámina. Cuanto más gruesa sea la lámina más cantidad de pasta de soldadura depositarás en tu placa. Las latas de refresco suelen estar fabricadas en aluminio de 0.1 milímetros de espesor. Verifica que el espesor de tu material sea el que deseas. 

### Químicos

A continuación se encuentra la lista de productos químicos utilizados en el Método I. Recuerda utilizar protección para manos, nariz y boca durante su uso. 

* Composición de la solución de revelado
  - 100mL de agua desionizada
  - 2g de Carbonato de Sodio (2% en peso)

* Composición del atacador químico (comercial)
  - 100mL de Ácido Clorhídrico al 33%
  - 36g de Persulfato Sódico

* Composición del agente de limpieza 
  - 100mL de Acetona pura

### Configuración de FlatCAM

* Isolation tool
  <pre>
      Tool Dia:       -0.207   (mm)
      Passes:         1
  </pre>

* Geometry tool
  <pre>
      Cut Z:          -0.2   (mm)
      Multi-Depth:    ⨯
      Travel Z:       1    (mm)
      Feedrate X-Y:   120  (mm/s)
      Feedrate Z:     25   (mm/s)
      Spindle Speed:  1000 (*)
  </pre>

_* NOTA (I): La máxima velocidad de giro de la máquina puede consultarse en la variable `$30` (Ejecuta el comando `$$` para inspeccionar el valor de todas las variables)_ 

_* NOTA (II): El diámetro de corte efectivo de la herramienta se puede calcular en el propio FlatCAM en el menú Tools -> Calculator. Para una fresa de 30º con una punta de 0.1mm a una profundidad de 0.2mm el diámetro efectivo de corte es de 0.207mm_ 

### Recursos adicionales

En el siguiente enlace encontrarás el proyecto junto con sus esquemas y ficheros Gerber:

<a href="https://www.pcbway.com/project/shareproject/Training_Board_for_PIC18F2550_e2cbbcd2.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>