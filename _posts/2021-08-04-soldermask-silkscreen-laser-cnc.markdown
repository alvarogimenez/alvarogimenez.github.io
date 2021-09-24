---
layout: post
title:  "Soldermask & Silkscreen con Láser + CNC: Tutorial completo"
date:   2021-08-04
categories: electronica
excerpt_separator: <!--more-->
# Low quality images in /assets/2021-02-12-cnc-1610-upgrade/low (https://bulkresizephotos.com/)
---

<a href="/assets/2021-08-04-soldermask-silkscreen-laser-cnc/main.jpg" >
<img 
  align="left" 
  src="/assets/2021-08-04-soldermask-silkscreen-laser-cnc/low/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

 
En el video que hoy publico presento el segundo tutorial de una serie sobre la producción de PCBs con máquinas CNC de bajo coste. En este caso abordaremos la creación de la máscara antisoldante (Soldermask) y la máscara de componentes (Silkscreen) utilizando un módulo láser y resinas curables por luz ultravioleta. 

Utilizaremos el software FlatCAM para crear los programas G-Code necesarios y analizaremos las configuraciones óptimas para cualquier módulo láser. Además, estudiaremos cómo aplicar correctamente la máscara y veremos una técnica para alinear el láser y reutilizar el alineamiento en futuras ocasiones. 

<!--more-->

### Parte III: Soldermask y Silkscreen con Laser y una CNC

A continuación puedes encontrar el tercer video de la serie. 

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/NuJlgw7E7vg" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Preguntas Frecuentes

* **¿Cómo puedo saber la potencia máxima que puedo configurar en mi CNC?**

Durante todo el tutorial hablo sobre el valor máximo configurado para la potencia de mi CNC refiriéndome a el con un valor de 1000. Para saber cuál es el valor máximo de cofniguración de potencia en tu CNC ejecuta el comando `$$` e inspecciona el valor de la variable `$30`. E.g.: Si el valor establecido es 1000, un 25% de potencia equivale a un valor de 250 como velocidad de giro del husillo. 

* **¿Cómo puedo saber la velocidad horizontal máxima que soporta mi CNC?**

Todas las plantillas de prueba utilizan una velocidad en el plano horizontal (FeedRate X-Y) de 1000 mm/min. Para saber cuál es la velocidad máxima que soporta tu CNC ejecuta el comando `$$` e inspecciona el valor de las variables `$110` (X-axis maximum rate) y `$111` (Y-axis maximum rate).

* **¿Cómo acoplo el láser a mi CNC?**

En el último apartado de [este artículo](/electronica/2021/02/12/cnc-1610-upgrade.html) muestro cómo configurar un láser a una controladora Woodpecker 3.2. Lamentablemente cada controladora tiene una forma diferente de acoplar el láser aunque la mayoría de ellas suele tener un puerto dedicado para conectar módulos con soporte a PWM. 

### Placas de prueba para calibrar el láser

<a href="/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap.jpg" >
<img 
  align="left" 
  src="/assets/2021-08-04-soldermask-silkscreen-laser-cnc/low/TestCncWidthOverlap.jpg" 
  alt="Main" 
  width="280"
/>
</a>

Las placas de prueba pueden servir para encontrar los valores óptimos de operación en función del desempeño del módulo láser en concreto que utilicemos. 

Como se explica en el tutorial, los valores escogidos no son críticos pero sí influyen en la calidad de los resultados. Un láser con potencia insuficiente puede no exponer por completo las áreas de soldadura dejando la placa inservible. Un láser configurado con potencia excesiva puede quemar la fibra de vidrio de la placa. Utiliza estas plantillas de prueba para analizar el desempeño de tu láser comenzando siempre por la potencia más baja e incrementándola si fuera necesario. 

Hay disponibles cuatro plantillas con valores de potencia fijos del 25%, 50%, 75% y 100% que puedes descargar a continuación:

* [Plantilla 25%](/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap_Power25.nc)
* [Plantilla 50%](/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap_Power50.nc)
* [Plantilla 75%](/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap_Power75.nc)
* [Plantilla 100%](/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap_Power100.nc)

Si necesitas un valor de potencia diferente a los anteriores, descarga el siguiente programa G-Code y, utilizando un editor de textos, sustituye el texto `_POWER_` por el valor que necesites:

* [Plantilla genérica _POWER_](/assets/2021-08-04-soldermask-silkscreen-laser-cnc/TestCncWidthOverlap_PowerWildcard.nc)
