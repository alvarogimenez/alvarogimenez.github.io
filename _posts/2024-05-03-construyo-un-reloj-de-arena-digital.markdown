---
layout: post
title:  "Construyo un reloj digital con...¡¿ARENA?!"
date:   2024-05-03
categories: electronica
excerpt_separator: <!--more-->
---

<a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/main.jpg" >
<img 
  align="left" 
  src="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

En este nuevo video exploramos una idea sobre la que he trabajado durante meses: traer a este siglo un diseño tan antiguo como el de un reloj de arena. Después de casi un año de investigación, diseño y más de 25 versiones e iteraciones del prototipo, os puedo enseñar, al fin, el resultado final de este precioso proyecto. 

Además de los resultados veremos todo el proceso de fabricación en detalle acompañado de animaciones creadas especialmente para ilustrar cada técnica utilizada. Persistencia de visión, pequeñas piezas de precisión mecanizadas en el taller, una PCB casera (como no podía ser de otro modo) y una sincronización al milisegundo. ¡Espero que lo disfrutéis! 

<!--more-->

<iframe class="center" width="560" height="400" style="margin-bottom:15px;" src="https://www.youtube.com/embed/_9PN4svCw48" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Números de arena

<a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/POCX4.jpg" >
<img 
  align="left" 
  src="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/POCX4.jpg" 
  alt="Main" 
  width="280"
/>
</a>

Uno de los retos principales del proyecto es formar un número en pleno vuelo en menos de una décima de segundo. El motivo de esta restricción de tiempo tiene que ver con la cantidad de veces que queremos mostrar el número por segundo y la persistencia de visión.Un objeto en caída libre tarda, aproximadamente, 100 milisegundos en caer una altura de 5 centímetros. De ese modo, si lo lanzamos periódicamente cada décima de segundo el objeto pasará por el mismo punto 10 veces por segundo. 

Para que el número caiga cada 100 milisegundos hasta una altura de 5 centímetros y exista cierto espacio entre el número y la plataforma desde la que cae, cada una de las celdas verticales que lo componen "mide" aproximadamente 15 milisegundos, es decir, es el resultado de abrir y dejar caer la arena durante tan sólo 15 milisegundos. 

A continuación os dejo el código de control Arduino necesario para mostrar los 10 números digitales de forma periódica en un módulo de 4 compuertas:

<pre style="max-height:500px;">
    {% raw %}
    <code class="cpp">
void setup() {
  pinMode(LED_BUILTIN, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(13, OUTPUT);

  set(0,0,0,0);
}

void light(int time) {
  digitalWrite(LED_BUILTIN, HIGH);
  delay(time);   
  digitalWrite(LED_BUILTIN, LOW); 
}

void set(int a, int b, int c, int d) {
  digitalWrite(12, a);
  digitalWrite(9, b);
  digitalWrite(11, c);
  digitalWrite(10, d);
}

int data[10][5][4] = {
    {{1,1,1,1},{1,0,0,1},{1,0,0,1},{1,0,0,1},{1,1,1,1}}, // 0
    {{0,0,0,1},{0,0,0,1},{0,0,0,1},{0,0,0,1},{0,0,0,1}}, // 1
    {{1,1,1,1},{0,0,0,1},{1,1,1,1},{1,0,0,0},{1,1,1,1}}, // 2
    {{1,1,1,1},{0,0,0,1},{1,1,1,1},{0,0,0,1},{1,1,1,1}}, // 3
    {{1,0,0,1},{1,0,0,1},{1,1,1,1},{0,0,0,1},{0,0,0,1}}, // 4
    {{1,1,1,1},{1,0,0,0},{1,1,1,1},{0,0,0,1},{1,1,1,1}}, // 5
    {{1,1,1,1},{1,0,0,0},{1,1,1,1},{1,0,0,1},{1,1,1,1}}, // 6        
    {{1,1,1,1},{0,0,0,1},{0,0,0,1},{0,0,0,1},{0,0,0,1}}, // 7
    {{1,1,1,1},{1,0,0,1},{1,1,1,1},{1,0,0,1},{1,1,1,1}}, // 8
    {{1,1,1,1},{1,0,0,1},{1,1,1,1},{0,0,0,1},{1,1,1,1}}, // 9
};

int delays[5] = {10, 8, 15, 10, 15};

void loop() {  
  int s = (millis()/1500) % 10;
  int vPixels = 5;
  for(int i = 0; i < vPixels; i++) {
    int * row = data[s][vPixels - 1 - i];
    set(row[0], row[1], row[2], row[3]);
    delay(delays[i]);
  }
  set(0,0,0,0);
  delay(35);
  light(5);
}
    {% endraw %}
    </code>
</pre>

## Recursos adicionales

Aquí podrás encontrar todos los recursos digitales empleados en este video. Este video está patrocinado por PCBWay. Echa un vistazo al siguiente enlace para conocer más detalles sobre el proyecto:

<a href="https://www.pcbway.com/project/shareproject/Header_extension_for_500W_Spindle_3d208834.html"><img src="https://www.pcbway.com/project/img/images/frompcbway-1220.png" alt="PCB from PCBWay" /></a>

A continuación puedes descargar los ficheros de diseño:

<table class="center">
    <tr>
        <td>
            <a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/MainPCB.jpg">
                <img 
                src="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/MainPCB.jpg" 
                width="150" />
            </a>
        </td>
        <td>
            <a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/DigitalSandClockV24 - CADCAM.ZIP">DigitalSandClockV24 - CADCAM.ZIP</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/X4Ctrl.jpg">
                <img 
                src="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/X4Ctrl.jpg" 
                width="150" />
            </a>
        </td>
        <td>
            <a href="/assets/2024-05-03-construyo-un-reloj-de-arena-digital/V26_ControllerX4_Mosfet - CADCAM.ZIP">V26_ControllerX4_Mosfet - CADCAM.ZIP</a>
        </td>
    </tr>
</table>