---
layout: post
title:  "DIY: Taladros metalizados en una PCB: Tutorial completo"
date:   2021-09-24
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2021-09-24-taladros-metalizados-pcb/main.jpg" >
<img 
  align="left" 
  src="/assets/2021-09-24-taladros-metalizados-pcb/low/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

 En el video que hoy publico vemos cómo metalizar o revestir de cobre los taladros de una PCB. Emplearemos una técnica denominada galvanoplastia o electrodeposición muy similar a la que se utiliza en los procesos industriales de producción de PCB.

 En este artículo, además de presentar el video, he recopilado algunas de las preguntas y problemas más frecuentes a la hora de abordar esta técnica. También podrás encontrar aquí un resumen de los productos y proporciones utilizados durante el proceso. 

<!--more-->

### Parte IV: Taladros metalizados en una PCB

A continuación puedes encontrar el cuarto video de la serie. 

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/fA78303EVQo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### Preguntas Frecuentes

* **¿Puedo no utilizar un agitador magnético?**

Sí, aunque es aconsejable utilizarlo. El agitador cumple dos propósitos: remover la solución, lo cual puede hacerse de forma manual, y mantener en movimiento el electrolito durante la fase de electrodeposición. Este último paso es importante para evitar que se formen óxidos o arbolaciones en la placa. Si no utilizas un agitador magnético simplemente reduce la corriente de electrodeposición (Por debajo de los 10mA/cm2) y aumenta el tiempo de exposición de forma proporcional. 

También puedes sustituir el agitador magnético por un sistema de agitación por aire, utilizando una bomba de aire de acuario y un tubo con varios agujeros sumergido en el electrolito por debajo de la placa. 

* **¿Qué sucede si no utilizo ácido clorhídrico?**

Si no empleamos ácido clorhídrico es muy posible que se formen óxidos en la placa. No subestimes la pequeña cantidad de 0.1 mililitros (2 gotas aproximadamente), es muy importante para que la placa se recubra de manera uniforme. Si, aún así, no dispones de ácido clorhídrico es posible realizar el proceso sin este químico reduciendo considerablemente la corriente de electrodeposición (Por debajo de los 7-10 mA/cm2).

* **¿Por qué utilizar Ácido Cítrico?**

Es cierto que la mayoría de los electrolitos acídicos suelen emplear Ácido Sulfúrico (H2SO4), incluidas las soluciones de galvanoplastia industriales. Sin embargo, en muchos países de la Union Europea incluido España, el país en el que resido actualmente, es necesario obtener una licencia para conseguir ácido sulfúrico que normalmente, para usos recreativos, es denegada. Esto es debido a que el ácido sulfúrico es ahora considerado como _precursor de explosivos_. Es por ello que decidí investigar alternativas y una de las más asequibles es el ácido cítrico, completamente legal y seguro de utilizar. Más información [aquí](http://www.interior.gob.es/es/web/servicios-al-ciudadano/precursores-de-explosivos).

* **Los taladros no se recubren de cobre, ¿Qué puede estar sucediendo?**

Puede deberse a varios factores:

1. Al lijar la superficie de la placa, tras activar los taladros, hicimos demasiada presión y se eliminó el contacto entre la superficie de la placa y el recubrimiendo de tinta conductiva. En este caso, debemos tratar de lijar la superficie con más cuidado, ejerciendo la mínima presión posible. 
2. La tinta conductiva no estaba bien agitada. Revisa la conectividad entre la cara superior e inferior de la placa tras secar la tinta conductiva. Si realizamos una medición de resistencia con un polímetro, la resistencia entre ambas caras no debería superar los 10 ohmios. 
3. Quizá necesites más tiempo. Si has reducido la corriente de electrodeposición por debajo de los 21.5mA/cm2, debes aumentar el tiempo de exposición de forma proporcional. 
4. No estás agitando correctamente el electrolito y las burbujas de aire atrapadas en el interior de los agujeros no permiten la electrodeposición. 

* **¿Qué sucede si no redondeo las esquinas de la placa?**

La corriente tiende a no distribuirse de manera uniforme en un conductor y siente especial predilección por los ángulos y esquinas. Redondeando los bordes de la placa ayudamos a la corriente a distribuirse de manera uniforme por la superficie de la placa y evitamos que se formen cúmulos de cobre y óxido o arbolaciones en torno a las esquinas debido a un incremento de la corriente en esas áreas. 

* **No tengo una fuente con limitador de corriente, ¿Puedo hacer el proceso con una pila o batería?**

No es aconsejable dado que el proceso de electrodeposición requiere de una fuente de corriente estable. Las fuentes de alimentación con regulador de corriente se encargarán de ajustar el voltaje para que la corriente se mantenga en el punto que hayamos fijado. Si utilizas una batería la corriente fluctuará a lo largo del proceso de electrodeposición según se formen las primeras capas de cobre y óxido en los electrodos. 

* **No tengo láminas de cobre, ¿Puedo utilizar tubos o alambre de cobre en su lugar?**

Sí, siempre y cuando revises que el material es cobre puro (y no aleaciones). La única implicación es que, al utilizar un electrodo que no sea plano y paralelo a la placa, la deposición de cobre puede ser menos uniforme. 

### Composición del electrolito y corriente de electrodeposición

A continuación puedes ver la composición exacta del electrolito para cualquier cantidad base de agua:

- Agua desionizada
- 250g/L de Sulfato de cobre pentahidratado (CuSO4·5H2O)
- 190g/L de Ácido Cítrico anhídro (C6H8O7)
- 0.35mL/L de Ácido Clorhídrico (HCl) al 20% (~7 gotas)
- 10mL/L de Polisorbato 20 (Opcional)

La corriente debe ser de 21.5mA/cm2 (~20ASF) y debe calcularse en base al área de cobre que queremos revestir. **Recuerda multiplicar por dos en caso de las placas a doble cara**. Con esta corriente y un tiempo de 40 minutos, deberíamos obtener una deposición de unas 20 micras. Si se reduce la corriente de electrodeposición, debemos aumentar proporcionalmente el tiempo de exposición. 

### Recursos adicionales

A continuación dejo los modelos 3D utilizados en este tutorial:

<table class="center">
    <tr>
        <td>
            <a href="/assets/2021-09-24-taladros-metalizados-pcb/PCB_PTH_Support.jpg">
                <img 
                src="/assets/2021-09-24-taladros-metalizados-pcb/low/PCB_PTH_Support.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2021-09-24-taladros-metalizados-pcb/PCB_PTH_Support.stl">PCB_PTH_Support.stl</a>
        </td>
    </tr>
</table>
