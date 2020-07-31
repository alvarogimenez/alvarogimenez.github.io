---
layout: post
title:  "Construyendo una caja de música"
date:   2020-08-10
categories: electronica
excerpt_separator: <!--more-->
hidden: true
# Low quality images in /assets/2020-08-10-construyendo-una-caja-de-musica/low (https://bulkresizephotos.com/)
---

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/main.jpg" >
<img 
  align="left" 
  src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/main.jpg" 
  alt="Main" 
  width="280"
/>
</a>

En el artículo de hoy vamos a analizar una peculiar caja de música que he diseñado y construido en los últimos meses. Las primeras cajas de música conocidas datan del siglo XVI y consistían en mecanismos giratorios similares a los utilizados en relojería. 

La caja de música que he construido es un cilindro con ocho cajones y un <a href="/electronica/2015/04/06/construyendo-un-zootropo-3d.htm">Zóotropo 3D</a> en su interior. Al abrir uno de los cajones se puede ver la tradicional animación de un personaje en movimiento salvo que, en esta ocasión, en lugar de ser un mecanismo mecánico, observamos el movimiento a través de un efecto estroboscópico. Cuantos más cajones abrimos, más personajes se iluminan en la escena mientras la música de la caja suena a través de un sistema que explicaré más adelante. Al cerrar todos los cajones la caja se apaga y permanece así hasta el siguiente uso. 

<!--more-->

<video class="center" controls preload>
  <source src="/assets/2020-08-10-construyendo-una-caja-de-musica/Main.mp4" type="video/mp4">
</video>

## Diseño

El diseño de esta caja de música consiste en un cilindro de 115mm de diámetro por 65mm de alto con ocho divisiones en las que podemos ver una ventana y un pequeño cajón. Al abrir cada cajón se muestra una animación en 3D de un personaje en movimiento a través del efecto estroboscópico mientras suena una música desde el interior de la caja. Para proteger el efecto estroboscópico de la luz exterior cada ventana estará cubierta con una lámina de cristal tintado. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/VistaGeneralAnim.png" >
<img 
  src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/VistaGeneralAnim.jpg"
  alt="Schematic" 
  class="center" />
</a>

A continuación muestro un video con animaciones del funcionamiento y secciones del dispositivo. Como se puede observar, al abrir uno de los cajones, el mecanismo central (en color blanco) comienza a girar y será iluminado con diodos LED de alta luminosidad situados en el estátor central. La coordinación del movimiento y el sonido están gobernados por la placa base situada en el centro de la caja. 

<video class="center" controls autoplay preload>
  <source src="/assets/2020-08-10-construyendo-una-caja-de-musica/Design.mp4" type="video/mp4">
</video>

El núcleo de esta caja de música es un motor N20 con una reducción de 250, lo que le permite girar a 60 revoluciones por minuto con un torque elevado. El rotor donde está situada la animación tiene ocho imanes, como se puede apreciar en la siguiente sección lateral, que excitan el sensor de efecto hall SS466a, permitiendo así conocer de forma precisa el momento en el que cada fotograma de la animación pasa por el ángulo de activación. Esto permitirá al controlador de la placa base iluminar únicamente la columna de LEDs del cajón que esté abierto en ese momento durante un instante de tiempo para lograr el efecto estroboscópico. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/CorteLateral.png" >
<img 
  src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/CorteLateral.jpg"
  alt="Schematic" 
  class="center" />
</a>

Veamos en detalle la construcción el estátor. Al rededor de esta pieza encontramos columnas de diodos LED (cuatro en cada columna). Estas columnas se pueden encender independientemente en función del cajón que se abra. Cada cajón está alineado con una columna de LEDs. Además, dentro del estátor, encontramos alojado el motor N20 que da movimiento al rotor y el sensor SS466a. En las siguientes imágenes se puede apreciar el rotor desde fuera y un corte transversal del mismo. 


<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleEstator.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleEstator.jpg"
alt="Schematic" 
class="center" />
</a>
<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleEstatorCorte.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleEstatorCorte.jpg"
alt="Schematic" 
class="center" />
</a>

El rotor consiste en un cilindro con ocho fotogramas. Estos fotogramas forman una animación reversible y cíclica que, gracias al efecto estroboscópico, se mostrara como un video a través de las ventanas de la caja de música. El rotor se compone de dos mitades para ajustarlo al tamaño máximo de impresión de la impresora 3D que vamos a utilizar y está ensamblado con 6 tornillos a una pieza en la parte superior. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleRotorAnim.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleRotorAnim.jpg"
alt="Schematic" 
class="center" />
</a>

El armazón de la caja de música está diseñado para alojar una batería de 9V en su parte inferior así como la placa base, de forma circular, en el centro. Tiene además las ventanas que permitirán apreciar cada animación de forma individual. Veamos a continuación algunas imágenes del armazón. 

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleCarcasa01.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleCarcasa01.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleCarcasa02.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleCarcasa02.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

La base de la caja de música tiene el acceso a la batería, un hueco para un interruptor general de apagado y, detrás de la tapa de la batería, un hueco con el conector ICSP de programación de la placa base. 

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleInferior.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleInferior.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleInferiorTapaAbierta.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleInferiorTapaAbierta.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

El mecanismo que permite que la caja se encienda cuando abrimos alguno de los cajones de su lateral está formado por un imán y un interruptor magnético de lengüeta. Cada cajón tiene un hueco cilíndrico para alojar un imán de neodimio de 5mm de diámetro. En cada extremo del armazón, situado justo en la parte superior del cajón, se encuentran los interruptores de lengüeta. Estos interruptores están normalmente abiertos durante el contacto con el imán. Al extraer el cajón y perder el contacto con el imán se cierran y activan un mecanismo eléctrico que detallo en la sección de Electrónica más adelante. Vemos en las siguientes imágenes el interruptor (en azul) y el hueco para el imán en el cajón. 


<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/CorteDetalleCajon.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/CorteDetalleCajon.jpg"
alt="Schematic" 
class="center" />
</a>
<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/CorteDetalleCajonAbierto.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/CorteDetalleCajonAbierto.jpg"
alt="Schematic" 
class="center" />
</a>

La música la reproduciremos a través de un altavoz en miniatura situado en el centro del armazón. En la siguiente imagen se puede apreciar el hueco para el altavoz y los agujeros para que el aire pueda desplazarse a través del hueco de la batería. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DetalleAltavoz.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DetalleAltavoz.jpg"
alt="Schematic" 
class="center" />
</a>


## Electrónica

La placa base está gobernada por un microcontrolador PIC18F2550. El controlador será el encargado de determinar qué columnas de LED estarán iluminadas y el momento preciso de la iluminación de cada fotograma. A través de un sensor de efecto hall y haciendo uso de las interrupciones hardware del controlador iluminaremos las columnas LED correspondientes a las secciones de la caja que se encuentren abiertas en cada momento. El controlador se encarga también de gobernar el motor y el altavoz utilizando PWM. En el siguiente fragmento del esquemático observamos el microcontrolador, la interfaz con el sensor SS466a (FES), la interfaz con el motor a través de un transistor MOSFET y la interfaz ISPC para programar el PIC. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/SchematicPic18f2550.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/SchematicPic18f2550.jpg"
alt="Schematic" 
class="center" />
</a>

Cada columna de LEDs está controlada por una salida del PIC18F2550 a través de un MOSFET BS170. En el siguiente fragmento del esquemático se pueden apreciar las ocho etapas de control de las columnas LED.

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/SchematicLedDriver.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/SchematicLedDriver.jpg"
alt="Schematic" 
class="center" />
</a>

Para que la caja se encienda al abrir una de las cajas y se apague con consumo cero al cerrar todas las cajas aislamos la tierra del circuito del terminal negativo de la batería a través de un MOSFET. Este mecanismo se encuentra replicado en las ocho columnas. Al activar uno de los interruptores de cualquier cajón su MOSFET correspondiente se activa y la corriente es capaz de fluir desde la tierra del circuito hasta el polo negativo de la batería. Además un diodo conecta cada puerta de cada etapa con una entrada en el PIC para saber qué cajones han sido abiertos. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/SchematicGateDriver.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/SchematicGateDriver.jpg"
alt="Schematic" 
class="center" />
</a>

Otra parte importante de la placa base es el amplificador de audio utilizado para reproducir la música que se escucha al activar la caja. El PIC18F2550 no tiene salida analógica así que es preciso simular la señal analógica de audio utilizando el ciclo activo del PWM. El PWM debe ser procesado con un filtro paso bajo y posteriormente amplificado utilizando un LM386. En la siguiente imagen se observa esta parte del esquemático.

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/SchematicSpeakerDriver.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/SchematicSpeakerDriver.jpg"
alt="Schematic" 
class="center" />
</a>

El diseño de la placa es algo complicado por la cantidad de componentes que tiene. La placa tiene forma circular con un diámetro de 70mm. Está pensada para tener el estátor que hemos visto en la sección anterior directamente adherido siguiendo el patrón que se muestra en la capa superior. El sensor de efecto hall SS466a se encuentra oculto tras una de las columnas del estátor y un potenciómetro multivuelta permite el ajuste del volumen de salida de la caja. 

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLayoutTop.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbLayoutTop.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLayoutBottom.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbLayoutBottom.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbTop.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbTop.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbBottom.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbBottom.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

Cada columna de LEDs también tiene una pequeña placa. El diseño de esta placa es muy sencillo y permite disponer los LEDs en pares paralelos para garantizar que la corriente que pasa por cada diodo es la adecuada. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/SchematicLed.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/SchematicLed.jpg"
alt="Schematic" 
style="max-width: 300px"
class="center" />
</a>

A continuación podemos ver el aspecto de la placa de diodos LED. Dispondremos un total de ocho copias de esta placa en el estátor utilizando los agujeros destinados a cada diodo como guías. 

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLayoutLed.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLayoutLed.png"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLed.png" >
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLed.png"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

## Firmware

El software necesario para que la caja funcione utiliza varias de las funciones disponibles (casi al máximo en algunos casos) en el PIC18F2550. Utilizamos todos los temporizadores e interrupciones del PIC para diferentes propósitos:

<ul>
    <li><b>INT0 e INT1:</b>Utilizaremos las interrupciones para capturar la subida y bajada de flanco del sensor SS466a. De este modo sabremos cuando el rotor ha girado 45 grados para iluminar durante un determinado tiempo las columnas de LED que se encuentren activas. </li>
    <li><b>TIMER 0:</b>Con este temporizador controlamos dos cosas. En primer lugar, una vez alcanzada la interrupción anterior, esperamos un determinado tiempo para que el rotor tenga tiempo de avanzar hasta estar en el ángulo correcto para ilumnar la escena. Esto es necesario porque el imán situado en cada columna del rotor activa el sensor SS466a algo antes de alcanzar el ángulo adecuado. En segundo lugar cargamos el TIMER0 con el tiempo que queremos iluminar la escena. Cuando más tiempo más brillante será la escena pero también más borrosa. </li>
    <li><b>TIMER 1:</b>Con este temporizador vamos a generar el PWM software para controlzar la velocidad del motor N20 que gobierna el rotor y así decidir la velocidad de la animación. </li>
    <li><b>TIMER 2:</b>Este temporizador es el que controla el PWM del audio. El audio es un muestreo de 2 segundos (16k samples a 8k como frecuencia de muestreo) de un DO4 grabado de una caja de música acústica. Por cada muestra del audio cambiaremos el ciclo activo del PWM que, al atravesar el filtro paso bajo, generará una señal analógica. </li>
    <li><b>TIMER 3:</b>Este temporizador lo utilizamos para analizar periódicamente cuantos cajones han sido abiertos. De esta forma cuando se abre un nuevo cajón actualizamos el <i>array</i> de columnas de LED activas y, por tanto, a iluminar en cada sincronización del temporizador 0.</li>
</ul>

<pre style="max-height:500px;">
    <code class="c">
#include <18F2550.h>
#FUSES NOWDT,VREGEN,NOMCLR
#USE delay(clock=48MHz, crystal=20MHz)
#use pwm(output=PIN_C0, timer=1, frequency=1kHz, duty=20)
#BYTE UCON = 0xF6D
#BYTE UCFG = 0xF6F 

#include "sample.h"

int16 boxes [] = { PIN_B2, PIN_B3, PIN_B4, PIN_B5, PIN_B6, PIN_B7, PIN_C6, PIN_C7 };
int16 active_boxes [] = {0, 0, 0, 0, 0, 0, 0, 0};

void turnOnAllBoxes(void) {
    for(int i = 0; i < 8; i++) {
        output_high(boxes[i]);
    }
}

void turnOnActiveBoxes(void) {
    for(int i = 0; i < 8; i++) {
        if(active_boxes[i]) {
            output_high(boxes[i]);
        }
    }
}

void turnOffAllBoxes(void) {
    for(int i = 0; i < 8; i++) {
        output_low(boxes[i]);
    }
}

void updateActiveBoxes(void) {
    active_boxes[0] = input(PIN_A0) ? TRUE : FALSE;
    active_boxes[1] = input(PIN_A1) ? TRUE : FALSE;
    active_boxes[2] = input(PIN_A2) ? TRUE : FALSE;
    active_boxes[3] = input(PIN_A3) ? TRUE : FALSE;
    active_boxes[4] = input(PIN_A4) ? TRUE : FALSE;
    active_boxes[5] = input(PIN_A5) ? TRUE : FALSE;
    active_boxes[6] = input(PIN_C4) ? TRUE : FALSE;
    active_boxes[7] = input(PIN_C5) ? TRUE : FALSE;
}

void playNote(int semitones, long duration_ms) {
    int delay_map[] = { 
        161,
        151,
        143,
        134,
        126, // C4
        119,
        112,
        106,
        100,
        94,
        89,
        83,
        79,
        74
    };
    int delay = delay_map[semitones];
    long duration_samples = (long)((double)(duration_ms)*1000/delay);
    long n_samples = (duration_samples > NUM_ELEMENTS) ? NUM_ELEMENTS : duration_samples;
    for(long i = 0; i < n_samples; i++) {
        set_pwm2_duty(data[i]);
        delay_us(delay);
    }
}

void main() {
    bit_clear(UCON,3);
    bit_set(UCFG,3);

    turnOffAllBoxes();
    delay_us(500);
    
    clear_interrupt(INT_RB);
    enable_interrupts(GLOBAL);
    enable_interrupts(INT_EXT_L2H);
    enable_interrupts(INT_EXT1_H2L);
    enable_interrupts(INT_TIMER0);  
    enable_interrupts(INT_TIMER3);

    setup_timer_0(T0_INTERNAL|T0_DIV_4);   
    setup_timer_2(T2_DIV_BY_1, 255, 1);
    setup_timer_3(T3_INTERNAL|T3_DIV_BY_8);
    setup_ccp2(CCP_PWM);
    
    set_timer3(0);
    
    delay_ms(500);
     
    for(int i = 0; i < 5; i++){
        // G#(4) C#(1) D#(1) E(1) F#(1) G#(3) E(1) G#(3) E(1) G#(3) C#(1) E(1) C#(1) G#(1) E(1) C#(8)
        // 12    5     7     8    10    12    8     12    8    12    5     8    5     12    8    5
        playNote(12, 2000);  
        playNote(5, 500);  
        playNote(7, 500);  
        playNote(8, 500); 
        playNote(10, 500);
        playNote(12, 1500); 
        playNote(8, 500);
        playNote(12, 1500);
        playNote(8, 500);
        playNote(12, 1500);
        playNote(5, 500);
        playNote(8, 500);
        playNote(5, 500);
        playNote(0, 500);
        playNote(8, 500);
        playNote(5, 4000);
    }
    
    setup_timer_0(T0_OFF);
    setup_timer_1(T1_DISABLED);
    setup_timer_2(T2_DISABLED, 1,1);
    setup_timer_3(T3_DISABLED);
    clear_interrupt(INT_RB);
    disable_interrupts(GLOBAL);
    disable_interrupts(INT_EXT_L2H);
    disable_interrupts(INT_EXT1_H2L);
    disable_interrupts(INT_TIMER0);  
    disable_interrupts(INT_TIMER3);
    turnOffAllBoxes();
    sleep();
}

int sync_wait = FALSE;

#INT_TIMER3
void TIMER3_isr(void) {
    updateActiveBoxes();
    set_timer3(0);
}

#INT_TIMER0
void TIMER0_isr(void) {
    if(sync_wait) {
        turnOnActiveBoxes();
        set_timer0(55000);  
        sync_wait = FALSE;
    } else {
        turnOffAllBoxes();
    }
}

void setupSyncWait(void) {
   set_timer0(30000);  
   sync_wait = TRUE;
}

#INT_EXT
void sensorL2H(void) {
   setupSyncWait();
}

#INT_EXT1
void sensorH2L(void) {
    setupSyncWait();
}
    </code>
</pre>

El siguiente fichero corresponde al muestreo del Do4 de la caja de música que utilizaremos para reproducir cada nota. Simplemente cambiando el retraso entre cada muestra del audio conseguimos las diferentes notas que necesitamos para la melodía. Es posible lograr hasta un total de dos octavas con simplemente una nota utilizando esta técnica.     

<pre style="max-height:400px;">
    <code class="c">
#ifndef SAMPLE_H
#define	SAMPLE_H


/**********************************************************************
* Written by WAVToCode
* Date:				Thu Jun 18 08:56:53 PM
* FileName:			Db1.C
* Interleaved:		Yes
* Signed:			No
* No. of channels:	1
* No. of samples:	15711
* Bits/Sample:		8
**********************************************************************/

#define NUM_ELEMENTS 13931

const int data[NUM_ELEMENTS] = {
126, 128, 126, 128, 128, 126, 128, 126, // 0-7
128, 134, 151, 171, 186, 190, 179, 154, // 8-15
123,  87,  53,  26,  16,  25,  52,  97, // 16-23
152, 203, 239,   0, 251, 230, 189, 136, // 24-31
 82,  33, 253, 238, 247,  22,  74, 139, // 32-39
200, 245,  14,  13, 245, 203, 152,  96, // 40-47
 45,   5, 240, 242,  17,  73, 144, 217, // 48-55
 11,  34,  27, 249, 194, 133,  77,  29, // 56-63
253, 239, 248,  24,  72, 130, 187, 229, // 64-71
253, 255, 236, 202, 159, 110,  62,  24, // 72-79
  1,   1,  22,  59, 108, 163, 208, 235, // 80-87
244, 236, 212, 176, 131,  84,  41,  12, // 88-95
  1,  14,  48,  94, 148, 196, 229, 243, // 96-103
239, 219, 187, 144,  97,  53,  19,   1, // 104-111
  8,  38,  81, 133, 184, 222, 241, 242, // 112-119
226, 197, 156, 110,  64,  27,   4,   4, // 120-127
 28,  68, 118, 172, 213, 238, 244, 232, // 128-135
206, 168, 123,  76,  36,   8,   1,  19, // 136-143
 55, 103, 157, 204, 232, 243, 236, 215, // 144-151
180, 136,  88,  46,  14,   2,  13,  44, // 152-159
 89, 142, 192, 225, 241, 238, 219, 188, // 160-167
147, 102,  60,  28,  12,  16,  43,  81, // 168-175
129, 176, 209, 227, 228, 214, 189, 156, // 176-183
115,  76,  43,  24,  23,  43,  76, 118, // 184-191
162, 197, 216, 221, 211, 190, 160, 124, // 192-199
 86,  54,  33,  29,  44,  74, 111, 152, // 200-207
187, 208, 215, 208, 191, 166, 134,  99, // 208-215
 67,  45,  35,  42,  68, 101, 139, 176, // 216-223
200, 211, 209, 195, 172, 142, 109,  76, // 224-231
 51,  37,  40,  60,  91, 128, 167, 194, // 232-239
208, 210, 199, 178, 151, 118,  85,  58, // 240-247
 40,  38,  53,  81, 116, 155, 186, 204, // 248-255
210, 203, 185, 160, 129,  97,  68,  48, // 256-263
 41,  50,  74, 106, 142, 176, 196, 204, // 264-271
202, 188, 166, 138, 107,  77,  56,  45, // 272-279
 50,  70,  99, 133, 165, 189, 199, 199, // 280-287
188, 170, 145, 115,  86,  64,  50,  51, // 288-295
 66,  92, 123, 155, 180, 194, 197, 191, // 296-303
174, 153, 125,  97,  72,  56,  51,  62, // 304-311
 85, 113, 146, 174, 191, 197, 192, 179, // 312-319
159, 133, 104,  79,  60,  52,  58,  78, // 320-327
105, 137, 166, 186, 196, 195, 183, 165, // 328-335
140, 113,  86,  65,  54,  57,  73,  98, // 336-343
128, 158, 179, 191, 192, 183, 168, 146, // 344-351
120,  95,  74,  61,  61,  72,  95, 120, // 352-359
148, 171, 184, 188, 182, 169, 151, 127, // 360-367
104,  83,  68,  63,  72,  91, 114, 141, // 368-375
164, 178, 184, 180, 170, 154, 133, 110, // 376-383
 88,  72,  65,  70,  86, 109, 134, 159, // 384-391
176, 184, 183, 175, 158, 138, 114,  92, // 392-399
 74,  65,  67,  80, 102, 128, 154, 173, // 400-407
184, 185, 178, 163, 143, 120,  97,  79, // 408-415
 68,  67,  78,  98, 121, 147, 168, 180, // 416-423
184, 178, 165, 146, 124, 102,  83,  71, // 424-431
 68,  77,  95, 119, 144, 166, 180, 183, // 432-439
177, 165, 147, 127, 105,  87,  74,  69, // 440-447
 76,  92, 114, 139, 162, 177, 182, 179, // 448-455
168, 152, 132, 111,  91,  77,  70,  74, // 456-463
 87, 107, 131, 155, 172, 180, 181, 171, // 464-471
157, 139, 117,  97,  81,  72,  73,  83, // 472-479
102, 124, 148, 168, 178, 180, 174, 161, // 480-487
144, 123, 102,  85,  75,  72,  80,  96, // 488-495
118, 141, 163, 177, 182, 177, 165, 149, // 496-503
128, 108,  89,  76,  70,  76,  91, 111, // 504-511
135, 158, 175, 181, 179, 169, 154, 135, // 512-519
113,  94,  79,  72,  73,  86, 106, 129, // 520-527
153, 171, 181, 182, 173, 158, 140, 119, // 528-535
 98,  81,  72,  72,  81,  99, 123, 147, // 536-543
167, 179, 181, 175, 163, 145, 124, 103, // 544-551
 86,  74,  71,  78,  94, 117, 140, 163, // 552-559
177, 182, 178, 166, 150, 130, 109,  91, // 560-567
 76,  70,  74,  89, 109, 133, 156, 174, // 568-575
181, 181, 171, 157, 137, 117,  96,  80, // 576-583
 71,  71,  83, 101, 124, 149, 169, 179, // 584-591
182, 176, 162, 144, 123, 102,  84,  72, // 592-599
 70,  79,  96, 118, 142, 163, 176, 182, // 600-607
178, 166, 150, 129, 108,  90,  76,  70, // 608-615
 75,  90, 110, 134, 156, 173, 180, 178, // 616-623
169, 155, 137, 116,  97,  82,  73,  74, // 624-631
 85, 104, 126, 149, 167, 177, 178, 171, // 632-639
159, 143, 122, 103,  86,  76,  73,  82, // 640-647
 98, 118, 141, 162, 174, 179, 175, 164, // 648-655
149, 129, 109,  91,  78,  73,  78,  93, // 656-663
112, 135, 156, 171, 178, 176, 168, 154, // 664-671
135, 114,  95,  80,  74,  75,  88, 106, // 672-679
128, 151, 169, 177, 179, 171, 159, 141, // 680-687
121, 100,  83,  73,  72,  82,  99, 121, // 688-695
144, 164, 175, 179, 175, 164, 148, 128, // 696-703
107,  89,  77,  72,  78,  94, 114, 137, // 704-711
158, 172, 177, 176, 167, 153, 134, 114, // 712-719
 95,  81,  75,  77,  89, 107, 129, 151, // 720-727
167, 175, 176, 169, 158, 141, 121, 102, // 728-735
 86,  76,  75,  84, 100, 120, 143, 161, // 736-743
172, 176, 172, 163, 148, 129, 109,  91, // 744-751
 78,  74,  79,  92, 111, 134, 154, 169, // 752-759
177, 176, 170, 158, 140, 119,  99,  82, // 760-767
 73,  74,  85, 102, 124, 147, 164, 175, // 768-775
179, 175, 165, 148, 127, 105,  87,  74, // 776-783
 70,  78,  94, 116, 139, 159, 173, 180, // 784-791
178, 169, 154, 133, 112,  91,  76,  69, // 792-799
 73,  87, 107, 131, 154, 170, 180, 180, // 800-807
174, 161, 142, 120,  98,  80,  70,  71, // 808-815
 82, 100, 123, 147, 165, 176, 181, 176, // 816-823
167, 148, 127, 105,  85,  72,  70,  79, // 824-831
 94, 116, 139, 159, 172, 178, 178, 170, // 832-839
154, 134, 112,  91,  77,  70,  75,  89, // 840-847
108, 131, 153, 168, 177, 178, 173, 160, // 848-855
142, 119,  98,  82,  72,  73,  84, 101, // 856-863
124, 146, 163, 175, 179, 176, 164, 147, // 864-871
125, 103,  84,  73,  72,  80,  96, 118, // 872-879
141, 160, 173, 179, 177, 168, 152, 132, // 880-887
109,  89,  75,  71,  78,  92, 112, 135, // 888-895
155, 169, 177, 177, 170, 156, 136, 115, // 896-903
 94,  80,  72,  76,  89, 108, 130, 151, // 904-911
166, 175, 177, 171, 158, 140, 120,  99, // 912-919
 83,  76,  76,  87, 103, 124, 145, 162, // 920-927
172, 175, 172, 162, 146, 126, 106,  88, // 928-935
 77,  76,  83,  98, 116, 136, 153, 165, // 936-943
171, 171, 165, 153, 136, 118, 100,  87, // 944-951
 81,  83,  93, 109, 128, 145, 159, 167, // 952-959
169, 166, 157, 142, 124, 106,  91,  82, // 960-967
 81,  89, 103, 121, 141, 155, 166, 171, // 968-975
169, 161, 147, 130, 111,  95,  83,  80, // 976-983
 85,  97, 114, 133, 150, 162, 169, 170, // 984-991
165, 152, 135, 117,  99,  86,  81,  84, // 992-999
 95, 111, 130, 148, 161, 169, 170, 166, // 1000-1007
154, 137, 120, 101,  87,  80,  83,  93, // 1008-1015
108, 127, 145, 159, 168, 170, 166, 156, // 1016-1023
141, 124, 106,  91,  82,  83,  92, 105, // 1024-1031
123, 142, 155, 164, 167, 165, 157, 144, // 1032-1039
127, 110,  95,  85,  83,  90, 102, 119, // 1040-1047
137, 153, 163, 168, 167, 160, 147, 131, // 1048-1055
114,  99,  87,  84,  87,  98, 114, 132, // 1056-1063
148, 159, 165, 166, 161, 152, 137, 121, // 1064-1071
105,  93,  86,  87,  95, 108, 125, 141, // 1072-1079
154, 162, 165, 163, 155, 142, 127, 111, // 1080-1087
 97,  88,  87,  93, 104, 120, 137, 151, // 1088-1095
160, 164, 163, 157, 145, 131, 115, 100, // 1096-1103
 90,  86,  91, 101, 116, 133, 148, 159, // 1104-1111
164, 164, 159, 147, 134, 118, 102,  91, // 1112-1119
 86,  89,  99, 113, 130, 146, 156, 161, // 1120-1127
160, 155, 147, 135, 121, 108,  99,  95, // 1128-1135
 97, 105, 115, 128, 140, 148, 152, 154, // 1136-1143
151, 144, 135, 125, 113, 105, 100, 100, // 1144-1151
105, 115, 126, 138, 146, 150, 152, 151, // 1152-1159
145, 137, 127, 116, 106, 100,  99, 103, // 1160-1167
112, 122, 133, 142, 148, 151, 150, 147, // 1168-1175
140, 131, 121, 110, 102,  99, 100, 107, // 1176-1183
117, 130, 141, 149, 152, 153, 150, 143, // 1184-1191
133, 122, 111, 103,  98,  99, 106, 115, // 1192-1199
128, 139, 148, 152, 154, 151, 145, 135, // 1200-1207
124, 114, 105,  99,  99, 104, 113, 125, // 1208-1215
136, 145, 150, 152, 151, 146, 138, 128, // 1216-1223
118, 108, 102, 100, 104, 111, 121, 133, // 1224-1231
143, 148, 151, 151, 147, 139, 131, 120, // 1232-1239
111, 103,  99, 102, 109, 118, 129, 139, // 1240-1247
146, 150, 151, 148, 143, 135, 125, 116, // 1248-1255
107, 102, 101, 105, 112, 123, 133, 142, // 1256-1263
147, 150, 151, 148, 140, 132, 122, 111, // 1264-1271
104, 100, 102, 108, 117, 128, 137, 145, // 1272-1279
150, 152, 151, 146, 137, 126, 114, 104, // 1280-1287
 99,  98, 104, 112, 123, 135, 143, 151, // 1288-1295
154, 155, 150, 140, 129, 117, 105,  97, // 1296-1303
 95,  99, 108, 120, 133, 144, 152, 156, // 1304-1311
157, 152, 144, 132, 119, 107,  97,  94, // 1312-1319
 97, 104, 116, 130, 142, 152, 157, 159, // 1320-1327
155, 146, 135, 121, 108,  98,  93,  95, // 1328-1335
102, 114, 127, 141, 150, 157, 159, 157, // 1336-1343
148, 137, 123, 109,  98,  92,  92, 100, // 1344-1351
111, 125, 139, 150, 157, 160, 159, 152, // 1352-1359
140, 127, 112, 100,  92,  90,  95, 106, // 1360-1367
120, 135, 148, 156, 161, 161, 156, 145, // 1368-1375
132, 118, 104,  93,  90,  94, 102, 115, // 1376-1383
130, 143, 153, 160, 161, 158, 148, 136, // 1384-1391
121, 107,  96,  90,  91,  99, 111, 127, // 1392-1399
141, 152, 159, 162, 160, 152, 139, 125, // 1400-1407
109,  97,  90,  90,  97, 108, 123, 137, // 1408-1415
150, 158, 163, 161, 155, 143, 129, 113, // 1416-1423
 99,  90,  89,  93, 104, 118, 133, 147, // 1424-1431
156, 162, 163, 159, 148, 134, 118, 103, // 1432-1439
 92,  87,  91,  99, 112, 129, 144, 154, // 1440-1447
162, 164, 160, 150, 136, 121, 106,  95, // 1448-1455
 89,  90,  99, 111, 126, 141, 152, 159, // 1456-1463
162, 159, 151, 138, 124, 110,  98,  91, // 1464-1471
 91,  97, 109, 123, 137, 149, 157, 161, // 1472-1479
159, 153, 142, 129, 114, 102,  93,  91, // 1480-1487
 95, 104, 117, 133, 145, 155, 160, 161, // 1488-1495
157, 147, 134, 119, 107,  96,  92,  94, // 1496-1503
101, 113, 128, 141, 152, 158, 160, 157, // 1504-1511
149, 137, 122, 109,  98,  93,  93, 100, // 1512-1519
112, 126, 139, 150, 157, 160, 157, 150, // 1520-1527
139, 125, 111, 100,  93,  92,  98, 109, // 1528-1535
123, 137, 149, 156, 160, 158, 152, 140, // 1536-1543
128, 114, 102,  95,  93,  97, 106, 120, // 1544-1551
134, 146, 155, 158, 158, 152, 143, 130, // 1552-1559
117, 105,  97,  94,  97, 105, 118, 131, // 1560-1567
143, 151, 157, 156, 152, 144, 132, 120, // 1568-1575
107, 100,  96,  98, 105, 117, 129, 141, // 1576-1583
150, 153, 154, 150, 143, 133, 122, 111, // 1584-1591
103,  98,  98, 105, 115, 126, 138, 147, // 1592-1599
152, 154, 152, 146, 137, 126, 115, 106, // 1600-1607
100,  98, 102, 111, 121, 133, 143, 149, // 1608-1615
153, 152, 148, 140, 130, 120, 110, 103, // 1616-1623
100, 101, 108, 118, 129, 139, 146, 151, // 1624-1631
152, 149, 142, 134, 123, 113, 104, 101, // 1632-1639
101, 106, 115, 125, 136, 145, 150, 151, // 1640-1647
149, 144, 136, 126, 116, 108, 103, 102, // 1648-1655
106, 114, 123, 134, 143, 148, 150, 149, // 1656-1663
145, 137, 128, 119, 110, 104, 103, 105, // 1664-1671
112, 120, 131, 140, 147, 149, 149, 145, // 1672-1679
139, 130, 120, 111, 105, 102, 105, 111, // 1680-1687
120, 131, 140, 146, 149, 148, 146, 140, // 1688-1695
131, 123, 114, 108, 103, 104, 110, 117, // 1696-1703
126, 136, 144, 148, 149, 146, 142, 135, // 1704-1711
126, 118, 111, 105, 104, 107, 114, 122, // 1712-1719
132, 140, 146, 148, 148, 144, 137, 129, // 1720-1727
121, 113, 107, 105, 106, 112, 120, 129, // 1728-1735
137, 142, 146, 147, 146, 140, 133, 125, // 1736-1743
116, 109, 105, 104, 109, 115, 125, 134, // 1744-1751
141, 146, 148, 147, 143, 135, 128, 119, // 1752-1759
111, 106, 104, 107, 113, 122, 132, 140, // 1760-1767
146, 148, 148, 144, 138, 130, 121, 112, // 1768-1775
106, 102, 104, 109, 119, 128, 139, 146, // 1776-1783
150, 151, 149, 143, 134, 124, 114, 105, // 1784-1791
100, 100, 105, 113, 124, 136, 145, 150, // 1792-1799
153, 153, 147, 139, 129, 118, 108, 101, // 1800-1807
 98, 101, 108, 119, 130, 141, 148, 153, // 1808-1815
154, 150, 143, 133, 122, 111, 103,  99, // 1816-1823
101, 107, 116, 128, 138, 146, 152, 152, // 1824-1831
151, 144, 135, 123, 113, 104, 100, 100, // 1832-1839
106, 114, 126, 137, 146, 152, 155, 153, // 1840-1847
147, 138, 126, 114, 104,  98,  96, 101, // 1848-1855
110, 122, 133, 144, 151, 155, 155, 151, // 1856-1863
142, 130, 119, 107,  99,  97, 100, 107, // 1864-1871
118, 130, 141, 150, 155, 156, 152, 144, // 1872-1879
133, 121, 110, 101,  97,  99, 105, 114, // 1880-1887
127, 138, 147, 154, 155, 153, 147, 136, // 1888-1895
124, 112, 104,  98,  98, 103, 112, 123, // 1896-1903
135, 145, 152, 155, 154, 148, 139, 127, // 1904-1911
116, 105,  99,  97, 101, 109, 120, 132, // 1912-1919
143, 151, 154, 155, 151, 142, 131, 119, // 1920-1927
108, 101,  98,  99, 107, 117, 129, 140, // 1928-1935
148, 153, 155, 152, 144, 135, 122, 111, // 1936-1943
102,  98, 100, 105, 115, 126, 137, 146, // 1944-1951
152, 154, 153, 146, 136, 126, 114, 105, // 1952-1959
 99,  99, 103, 112, 123, 134, 143, 151, // 1960-1967
154, 154, 148, 140, 129, 118, 107, 100, // 1968-1975
 98, 101, 108, 119, 131, 142, 150, 154, // 1976-1983
156, 151, 143, 133, 120, 110, 101,  98, // 1984-1991
 99, 105, 115, 127, 139, 147, 153, 155, // 1992-1999
153, 146, 135, 124, 113, 103,  98,  99, // 2000-2007
103, 112, 124, 135, 145, 151, 155, 154, // 2008-2015
147, 139, 127, 115, 106,  99,  97, 100, // 2016-2023
109, 120, 132, 143, 150, 155, 155, 151, // 2024-2031
142, 132, 119, 109, 100,  98, 100, 106, // 2032-2039
117, 129, 140, 148, 153, 155, 152, 144, // 2040-2047
134, 122, 112, 103,  98,  98, 103, 113, // 2048-2055
125, 136, 146, 153, 156, 154, 148, 139, // 2056-2063
127, 114, 104,  97,  96,  99, 108, 121, // 2064-2071
134, 145, 152, 157, 157, 151, 142, 130, // 2072-2079
117, 106,  98,  95,  98, 106, 117, 131, // 2080-2087
142, 152, 156, 157, 153, 145, 133, 120, // 2088-2095
108,  99,  95,  97, 103, 114, 127, 138, // 2096-2103
149, 156, 157, 155, 147, 137, 125, 112, // 2104-2111
102,  96,  96, 101, 110, 123, 136, 146, // 2112-2119
153, 157, 156, 150, 141, 128, 116, 104, // 2120-2127
 97,  95,  98, 107, 119, 133, 144, 152, // 2128-2135
157, 157, 152, 143, 131, 119, 107,  99, // 2136-2143
 95,  98, 104, 116, 128, 140, 150, 156, // 2144-2151
158, 154, 146, 135, 122, 109, 100,  95, // 2152-2159
 95, 102, 112, 125, 138, 149, 156, 159, // 2160-2167
157, 149, 138, 126, 112, 101,  95,  94, // 2168-2175
 99, 109, 121, 135, 146, 155, 159, 158, // 2176-2183
152, 142, 128, 115, 103,  96,  93,  97, // 2184-2191
106, 119, 132, 144, 154, 160, 160, 154, // 2192-2199
144, 131, 117, 105,  96,  93,  94, 102, // 2200-2207
115, 130, 143, 153, 159, 160, 155, 146, // 2208-2215
135, 121, 108,  99,  94,  94, 100, 112, // 2216-2223
125, 138, 150, 157, 159, 156, 149, 138, // 2224-2231
125, 112, 102,  96,  94,  99, 109, 122, // 2232-2239
135, 146, 155, 159, 158, 151, 142, 129, // 2240-2247
116, 105,  97,  94,  97, 105, 117, 131, // 2248-2255
144, 153, 159, 159, 154, 145, 133, 120, // 2256-2263
108,  98,  94,  95, 102, 113, 127, 140, // 2264-2271
151, 158, 160, 157, 148, 137, 123, 111, // 2272-2279
100,  94,  95, 100, 110, 123, 136, 148, // 2280-2287
156, 159, 156, 150, 139, 127, 114, 104, // 2288-2295
 97,  95,  99, 108, 121, 133, 144, 152, // 2296-2303
157, 156, 150, 142, 130, 118, 107, 100, // 2304-2311
 97,  99, 106, 117, 130, 140, 149, 154, // 2312-2319
155, 151, 143, 133, 122, 110, 102,  98, // 2320-2327
 98, 104, 114, 126, 138, 147, 153, 156, // 2328-2335
153, 146, 137, 126, 115, 105,  99,  98, // 2336-2343
101, 110, 121, 133, 144, 151, 156, 156, // 2344-2351
150, 141, 131, 118, 107, 100,  96,  99, // 2352-2359
106, 117, 129, 141, 150, 156, 156, 153, // 2360-2367
145, 134, 121, 111, 101,  97,  98, 103, // 2368-2375
112, 125, 138, 148, 155, 157, 155, 148, // 2376-2383
137, 125, 113, 103,  97,  96, 101, 111, // 2384-2391
123, 135, 146, 153, 157, 155, 148, 139, // 2392-2399
127, 115, 105,  99,  96, 100, 108, 121, // 2400-2407
133, 144, 152, 156, 155, 150, 142, 130, // 2408-2415
118, 107, 101,  97,  99, 106, 117, 129, // 2416-2423
141, 150, 155, 157, 152, 144, 133, 122, // 2424-2431
111, 102,  98,  99, 104, 114, 126, 138, // 2432-2439
148, 154, 156, 153, 146, 137, 125, 113, // 2440-2447
104,  99,  97, 101, 109, 122, 133, 145, // 2448-2455
153, 157, 156, 150, 141, 130, 118, 108, // 2456-2463
100,  97,  98, 105, 117, 129, 141, 150, // 2464-2471
156, 157, 153, 144, 134, 123, 111, 103, // 2472-2479
 97,  97, 103, 112, 124, 136, 146, 154, // 2480-2487
156, 155, 148, 139, 128, 116, 106,  99, // 2488-2495
 97, 100, 108, 119, 132, 143, 151, 155, // 2496-2503
155, 150, 142, 131, 120, 109, 101,  97, // 2504-2511
 99, 105, 116, 128, 139, 148, 154, 156, // 2512-2519
152, 145, 135, 124, 112, 104,  98,  98, // 2520-2527
102, 112, 124, 134, 145, 152, 155, 152, // 2528-2535
147, 139, 128, 116, 107, 101,  99, 102, // 2536-2543
110, 121, 133, 143, 150, 154, 153, 148, // 2544-2551
139, 129, 118, 109, 103, 100, 103, 109, // 2552-2559
119, 130, 139, 148, 152, 153, 149, 141, // 2560-2567
132, 122, 112, 104, 101, 101, 107, 116, // 2568-2575
126, 137, 145, 150, 152, 150, 144, 135, // 2576-2583
125, 116, 108, 103, 102, 105, 114, 123, // 2584-2591
133, 141, 148, 151, 150, 145, 137, 129, // 2592-2599
118, 110, 104, 102, 103, 110, 121, 131, // 2600-2607
140, 148, 152, 151, 147, 140, 130, 121, // 2608-2615
112, 105, 102, 103, 108, 118, 128, 137, // 2616-2623
145, 151, 151, 148, 142, 134, 125, 115, // 2624-2631
108, 103, 103, 106, 114, 124, 134, 143, // 2632-2639
149, 151, 149, 144, 138, 128, 118, 110, // 2640-2647
104, 101, 104, 111, 121, 131, 140, 147, // 2648-2655
151, 151, 147, 141, 131, 121, 112, 105, // 2656-2663
101, 102, 108, 117, 127, 137, 146, 151, // 2664-2671
152, 149, 142, 135, 124, 115, 106, 101, // 2672-2679
101, 106, 115, 125, 136, 145, 151, 153, // 2680-2687
150, 145, 136, 126, 115, 107, 102, 100, // 2688-2695
103, 112, 122, 133, 143, 150, 153, 153, // 2696-2703
148, 140, 130, 119, 109, 103,  99, 101, // 2704-2711
107, 117, 128, 139, 148, 153, 153, 150, // 2712-2719
143, 134, 123, 113, 105, 100, 100, 105, // 2720-2727
115, 126, 137, 146, 151, 153, 151, 145, // 2728-2735
136, 125, 115, 107, 101,  99, 103, 112, // 2736-2743
122, 134, 144, 151, 154, 151, 146, 138, // 2744-2751
128, 117, 108, 101,  99, 102, 110, 121, // 2752-2759
132, 143, 150, 154, 153, 148, 140, 130, // 2760-2767
119, 110, 102,  99, 100, 107, 118, 130, // 2768-2775
141, 150, 155, 154, 150, 143, 133, 122, // 2776-2783
111, 103,  98,  98, 104, 114, 126, 138, // 2784-2791
147, 154, 155, 152, 145, 136, 125, 114, // 2792-2799
105,  99,  97, 101, 110, 122, 135, 146, // 2800-2807
154, 156, 155, 150, 141, 130, 117, 106, // 2808-2815
 99,  96,  98, 105, 117, 130, 142, 152, // 2816-2823
157, 156, 152, 144, 133, 120, 109, 100, // 2824-2831
 95,  96, 103, 115, 127, 140, 150, 157, // 2832-2839
157, 153, 146, 136, 123, 110, 101,  95, // 2840-2847
 95, 100, 111, 125, 139, 149, 157, 159, // 2848-2855
157, 149, 138, 126, 112, 102,  95,  94, // 2856-2863
 98, 108, 121, 135, 147, 156, 159, 157, // 2864-2871
151, 141, 129, 115, 104,  96,  93,  96, // 2872-2879
104, 118, 132, 145, 155, 159, 158, 153, // 2880-2887
144, 132, 119, 107,  98,  94,  95, 103, // 2888-2895
114, 129, 141, 152, 158, 158, 154, 146, // 2896-2903
135, 123, 111, 102,  96,  96, 100, 111, // 2904-2911
124, 136, 148, 155, 158, 155, 149, 138, // 2912-2919
127, 115, 104,  98,  95,  99, 108, 121, // 2920-2927
134, 145, 154, 158, 157, 151, 142, 130, // 2928-2935
118, 108,  99,  95,  97, 105, 117, 130, // 2936-2943
141, 151, 156, 157, 152, 145, 134, 123, // 2944-2951
111, 101,  96,  97, 103, 113, 125, 138, // 2952-2959
148, 155, 156, 153, 146, 137, 125, 114, // 2960-2967
104,  99,  97, 101, 111, 123, 135, 146, // 2968-2975
154, 157, 155, 149, 140, 129, 117, 107, // 2976-2983
 99,  96,  98, 105, 118, 131, 143, 152, // 2984-2991
157, 156, 152, 144, 132, 121, 109, 100, // 2992-2999
 97,  97, 103, 114, 128, 141, 150, 156, // 3000-3007
157, 153, 146, 136, 124, 112, 103,  97, // 3008-3015
 97, 101, 112, 124, 137, 148, 155, 157, // 3016-3023
154, 148, 138, 127, 115, 105,  99,  97, // 3024-3031
100, 108, 121, 133, 144, 152, 155, 154, // 3032-3039
149, 141, 131, 119, 109, 102,  99,  99, // 3040-3047
107, 118, 131, 142, 150, 154, 154, 149, // 3048-3055
142, 132, 121, 111, 103,  99,  99, 105, // 3056-3063
115, 128, 139, 149, 154, 155, 151, 144, // 3064-3071
135, 124, 113, 105, 100,  98, 102, 112, // 3072-3079
123, 135, 146, 153, 155, 152, 147, 138, // 3080-3087
127, 116, 107, 101,  98, 101, 108, 121, // 3088-3095
133, 144, 151, 155, 153, 148, 140, 130, // 3096-3103
119, 109, 102,  98, 100, 106, 117, 130, // 3104-3111
141, 150, 155, 155, 150, 143, 134, 123, // 3112-3119
112, 104,  98,  98, 103, 113, 126, 138, // 3120-3127
148, 154, 155, 152, 145, 136, 125, 115, // 3128-3135
106, 100,  99, 101, 110, 122, 134, 145, // 3136-3143
152, 154, 152, 147, 140, 129, 118, 109, // 3144-3151
102,  98, 100, 107, 118, 130, 142, 149, // 3152-3159
154, 154, 150, 142, 133, 122, 112, 104, // 3160-3167
 98,  99, 103, 114, 126, 138, 147, 153, // 3168-3175
154, 151, 145, 137, 126, 115, 106, 100, // 3176-3183
 98, 102, 110, 122, 134, 145, 151, 154, // 3184-3191
153, 148, 139, 129, 118, 108, 100,  97, // 3192-3199
100, 107, 119, 132, 143, 151, 155, 154, // 3200-3207
150, 142, 132, 121, 109, 102,  98,  99, // 3208-3215
104, 115, 128, 141, 150, 155, 155, 151, // 3216-3223
143, 134, 123, 113, 103,  98,  98, 103, // 3224-3231
113, 126, 138, 147, 153, 154, 151, 145, // 3232-3239
136, 125, 115, 106, 100,  99, 103, 111, // 3240-3247
124, 136, 145, 151, 153, 151, 145, 137, // 3248-3255
127, 117, 109, 103, 100, 103, 111, 121, // 3256-3263
133, 142, 150, 152, 150, 146, 138, 129, // 3264-3271
120, 110, 104, 101, 103, 108, 118, 130, // 3272-3279
140, 148, 152, 151, 147, 140, 131, 122, // 3280-3287
113, 106, 101, 101, 106, 115, 127, 138, // 3288-3295
147, 152, 153, 149, 143, 135, 124, 115, // 3296-3303
106, 101, 100, 104, 113, 124, 136, 145, // 3304-3311
151, 153, 150, 145, 136, 126, 117, 108, // 3312-3319
102, 100, 103, 110, 122, 133, 143, 150, // 3320-3327
153, 151, 146, 139, 129, 119, 110, 104, // 3328-3335
100, 102, 109, 119, 130, 140, 149, 151, // 3336-3343
152, 147, 140, 132, 122, 113, 106, 102, // 3344-3351
102, 107, 116, 127, 138, 146, 150, 151, // 3352-3359
147, 142, 134, 124, 116, 108, 103, 102, // 3360-3367
106, 113, 123, 134, 142, 148, 149, 149, // 3368-3375
143, 136, 128, 120, 112, 107, 104, 106, // 3376-3383
111, 120, 130, 139, 145, 148, 149, 145, // 3384-3391
139, 132, 123, 115, 109, 105, 104, 108, // 3392-3399
116, 127, 136, 143, 147, 148, 146, 141, // 3400-3407
134, 126, 118, 111, 106, 105, 107, 113, // 3408-3415
123, 133, 141, 147, 148, 147, 143, 136, // 3416-3423
129, 120, 113, 108, 105, 106, 112, 120, // 3424-3431
130, 139, 145, 148, 148, 144, 138, 131, // 3432-3439
123, 115, 109, 105, 105, 109, 118, 127, // 3440-3447
136, 143, 147, 148, 145, 140, 133, 125, // 3448-3455
118, 111, 106, 105, 109, 115, 124, 134, // 3456-3463
141, 146, 148, 146, 141, 136, 127, 120, // 3464-3471
112, 107, 105, 107, 113, 122, 132, 140, // 3472-3479
145, 148, 147, 142, 137, 130, 122, 114, // 3480-3487
108, 106, 106, 111, 120, 130, 138, 145, // 3488-3495
148, 147, 144, 137, 130, 122, 115, 109, // 3496-3503
106, 107, 111, 119, 128, 138, 144, 148, // 3504-3511
148, 144, 138, 131, 123, 116, 109, 106, // 3512-3519
106, 110, 117, 127, 136, 144, 148, 149, // 3520-3527
145, 140, 133, 126, 118, 111, 106, 106, // 3528-3535
108, 115, 124, 133, 141, 146, 148, 146, // 3536-3543
141, 135, 128, 121, 114, 109, 107, 108, // 3544-3551
113, 121, 130, 139, 144, 147, 146, 142, // 3552-3559
136, 130, 122, 116, 110, 108, 108, 111, // 3560-3567
119, 128, 136, 142, 146, 145, 143, 138, // 3568-3575
131, 124, 118, 111, 108, 108, 111, 118, // 3576-3583
126, 134, 142, 145, 146, 142, 137, 132, // 3584-3591
125, 118, 113, 109, 109, 111, 117, 125, // 3592-3599
133, 140, 144, 145, 143, 138, 133, 127, // 3600-3607
121, 114, 111, 109, 111, 115, 122, 131, // 3608-3615
139, 144, 145, 143, 140, 134, 128, 121, // 3616-3623
116, 111, 110, 110, 114, 121, 129, 137, // 3624-3631
142, 145, 143, 140, 135, 129, 123, 117, // 3632-3639
112, 110, 111, 113, 119, 127, 135, 141, // 3640-3647
144, 144, 142, 136, 132, 125, 119, 114, // 3648-3655
111, 110, 112, 117, 125, 132, 139, 143, // 3656-3663
144, 143, 138, 133, 127, 120, 116, 111, // 3664-3671
110, 111, 116, 122, 130, 138, 142, 144, // 3672-3679
144, 140, 135, 129, 122, 116, 112, 110, // 3680-3687
110, 114, 120, 128, 136, 141, 145, 144, // 3688-3695
142, 137, 131, 124, 118, 112, 110, 110, // 3696-3703
112, 118, 126, 135, 141, 145, 145, 143, // 3704-3711
138, 132, 126, 119, 114, 110, 108, 111, // 3712-3719
116, 123, 133, 139, 144, 146, 144, 140, // 3720-3727
133, 127, 121, 114, 110, 108, 110, 114, // 3728-3735
121, 130, 138, 143, 146, 145, 142, 135, // 3736-3743
129, 122, 116, 111, 109, 108, 113, 119, // 3744-3751
128, 136, 142, 145, 146, 142, 137, 131, // 3752-3759
124, 118, 112, 108, 109, 111, 116, 125, // 3760-3767
133, 141, 144, 145, 143, 139, 132, 126, // 3768-3775
119, 114, 110, 108, 110, 116, 123, 132, // 3776-3783
139, 144, 145, 144, 140, 134, 128, 120, // 3784-3791
115, 110, 109, 110, 114, 121, 129, 137, // 3792-3799
143, 146, 145, 142, 136, 130, 123, 116, // 3800-3807
111, 108, 109, 112, 118, 127, 135, 142, // 3808-3815
145, 144, 142, 137, 131, 124, 118, 113, // 3816-3823
109, 109, 112, 117, 125, 134, 140, 144, // 3824-3831
145, 143, 138, 133, 126, 120, 115, 110, // 3832-3839
110, 111, 116, 123, 131, 138, 143, 144, // 3840-3847
144, 139, 134, 128, 122, 117, 113, 110, // 3848-3855
111, 115, 120, 128, 135, 141, 143, 143, // 3856-3863
141, 136, 130, 124, 118, 114, 111, 111, // 3864-3871
114, 119, 126, 133, 138, 143, 143, 141, // 3872-3879
137, 132, 126, 121, 115, 112, 110, 112, // 3880-3887
116, 123, 131, 137, 142, 144, 142, 140, // 3888-3895
134, 129, 123, 117, 113, 110, 111, 114, // 3896-3903
121, 128, 135, 141, 143, 143, 141, 136, // 3904-3911
130, 125, 119, 114, 111, 110, 113, 118, // 3912-3919
125, 133, 139, 143, 143, 141, 137, 132, // 3920-3927
127, 120, 116, 112, 111, 112, 116, 123, // 3928-3935
131, 138, 141, 143, 142, 138, 134, 129, // 3936-3943
123, 117, 113, 111, 111, 115, 122, 129, // 3944-3951
135, 140, 142, 142, 139, 135, 130, 125, // 3952-3959
119, 115, 112, 112, 114, 119, 126, 133, // 3960-3967
139, 141, 142, 140, 136, 132, 127, 121, // 3968-3975
116, 112, 111, 113, 117, 124, 131, 137, // 3976-3983
141, 142, 141, 138, 133, 128, 123, 117, // 3984-3991
113, 111, 112, 116, 122, 129, 135, 140, // 3992-3999
142, 142, 139, 135, 130, 124, 119, 114, // 4000-4007
112, 112, 115, 121, 127, 134, 139, 141, // 4008-4015
142, 139, 136, 132, 126, 120, 114, 112, // 4016-4023
111, 114, 118, 125, 133, 138, 141, 142, // 4024-4031
141, 138, 133, 127, 122, 117, 113, 111, // 4032-4039
113, 117, 123, 130, 136, 140, 142, 141, // 4040-4047
139, 135, 129, 124, 118, 113, 111, 112, // 4048-4055
115, 121, 128, 135, 139, 142, 142, 139, // 4056-4063
135, 131, 125, 119, 114, 111, 111, 114, // 4064-4071
119, 126, 133, 138, 142, 143, 142, 138, // 4072-4079
133, 127, 121, 115, 111, 110, 111, 117, // 4080-4087
123, 131, 137, 142, 143, 143, 139, 134, // 4088-4095
129, 122, 117, 112, 111, 112, 116, 123, // 4096-4103
130, 136, 140, 142, 142, 139, 135, 129, // 4104-4111
124, 118, 114, 111, 112, 115, 121, 128, // 4112-4119
134, 139, 142, 142, 140, 136, 131, 125, // 4120-4127
120, 114, 112, 112, 114, 119, 125, 132, // 4128-4135
137, 141, 141, 140, 136, 132, 127, 122, // 4136-4143
117, 113, 112, 113, 117, 123, 130, 136, // 4144-4151
140, 142, 141, 139, 134, 129, 123, 118, // 4152-4159
114, 111, 112, 116, 122, 129, 135, 139, // 4160-4167
142, 141, 140, 135, 130, 124, 119, 114, // 4168-4175
111, 112, 114, 120, 127, 134, 139, 142, // 4176-4183
142, 140, 136, 132, 126, 120, 115, 112, // 4184-4191
111, 114, 119, 125, 132, 138, 141, 142, // 4192-4199
140, 137, 132, 126, 121, 116, 112, 111, // 4200-4207
113, 118, 124, 131, 136, 140, 143, 142, // 4208-4215
138, 133, 128, 123, 117, 113, 112, 113, // 4216-4223
116, 122, 129, 135, 139, 142, 142, 139, // 4224-4231
135, 129, 124, 119, 114, 112, 113, 115, // 4232-4239
120, 128, 133, 138, 142, 141, 139, 136, // 4240-4247
130, 125, 119, 115, 113, 113, 115, 119, // 4248-4255
126, 132, 137, 141, 141, 140, 137, 132, // 4256-4263
126, 121, 117, 113, 112, 114, 118, 124, // 4264-4271
130, 135, 140, 142, 140, 138, 134, 129, // 4272-4279
123, 118, 114, 113, 114, 116, 123, 128, // 4280-4287
135, 138, 141, 140, 138, 134, 129, 125, // 4288-4295
120, 116, 114, 115, 117, 122, 128, 133, // 4296-4303
138, 140, 140, 137, 134, 130, 125, 121, // 4304-4311
117, 114, 114, 116, 121, 126, 131, 135, // 4312-4319
138, 139, 138, 135, 131, 127, 122, 119, // 4320-4327
116, 116, 117, 119, 124, 130, 134, 136, // 4328-4335
138, 137, 135, 132, 128, 124, 121, 117, // 4336-4343
117, 117, 119, 123, 128, 132, 135, 137, // 4344-4351
136, 134, 132, 129, 126, 122, 119, 118, // 4352-4359
118, 119, 122, 127, 130, 134, 136, 136, // 4360-4367
135, 133, 130, 127, 124, 120, 119, 117, // 4368-4375
118, 120, 125, 130, 133, 135, 137, 136, // 4376-4383
134, 131, 128, 125, 121, 119, 118, 118, // 4384-4391
120, 124, 128, 131, 135, 135, 136, 134, // 4392-4399
132, 129, 126, 123, 120, 118, 119, 120, // 4400-4407
122, 126, 130, 132, 134, 135, 134, 132, // 4408-4415
130, 128, 124, 121, 119, 119, 119, 122, // 4416-4423
126, 129, 132, 134, 135, 134, 133, 131, // 4424-4431
128, 126, 122, 120, 120, 119, 120, 124, // 4432-4439
127, 130, 133, 134, 134, 134, 132, 130, // 4440-4447
127, 124, 122, 120, 119, 121, 123, 126, // 4448-4455
129, 131, 133, 133, 133, 132, 130, 127, // 4456-4463
126, 123, 121, 120, 120, 122, 125, 128, // 4464-4471
130, 132, 133, 133, 132, 130, 129, 127, // 4472-4479
124, 122, 121, 120, 122, 125, 127, 129, // 4480-4487
131, 132, 133, 133, 131, 129, 127, 124, // 4488-4495
122, 121, 120, 121, 123, 127, 129, 131, // 4496-4503
132, 134, 134, 133, 130, 128, 125, 122, // 4504-4511
120, 119, 120, 122, 125, 128, 131, 132, // 4512-4519
134, 134, 134, 132, 129, 126, 123, 121, // 4520-4527
119, 119, 121, 123, 126, 130, 132, 134, // 4528-4535
134, 134, 132, 130, 127, 124, 122, 119, // 4536-4543
118, 120, 122, 126, 129, 131, 133, 135, // 4544-4551
135, 133, 130, 128, 125, 121, 119, 119, // 4552-4559
120, 122, 125, 129, 132, 133, 135, 134, // 4560-4567
133, 131, 128, 125, 122, 119, 119, 119, // 4568-4575
122, 125, 128, 131, 133, 134, 134, 133, // 4576-4583
131, 129, 126, 123, 121, 119, 119, 121, // 4584-4591
124, 128, 130, 132, 134, 134, 133, 132, // 4592-4599
129, 126, 123, 120, 119, 119, 121, 124, // 4600-4607
127, 130, 133, 134, 134, 134, 132, 130, // 4608-4615
126, 124, 121, 120, 119, 120, 122, 126, // 4616-4623
129, 132, 133, 134, 134, 133, 131, 128, // 4624-4631
125, 122, 120, 120, 120, 122, 124, 127, // 4632-4639
131, 133, 133, 133, 132, 131, 129, 126, // 4640-4647
123, 121, 120, 120, 122, 125, 127, 129, // 4648-4655
132, 132, 133, 132, 131, 129, 127, 124, // 4656-4663
122, 121, 121, 122, 124, 127, 129, 131, // 4664-4671
132, 132, 132, 131, 129, 127, 125, 123, // 4672-4679
121, 121, 121, 124, 126, 129, 130, 132, // 4680-4687
132, 132, 131, 129, 128, 125, 123, 122, // 4688-4695
120, 121, 123, 126, 129, 131, 133, 133, // 4696-4703
133, 132, 130, 128, 126, 124, 121, 120, // 4704-4711
120, 121, 124, 127, 130, 131, 134, 134, // 4712-4719
133, 131, 130, 127, 124, 121, 120, 120, // 4720-4727
120, 122, 126, 129, 131, 133, 133, 133, // 4728-4735
132, 131, 128, 125, 122, 121, 120, 120, // 4736-4743
123, 126, 129, 131, 133, 134, 134, 133, // 4744-4751
131, 128, 125, 123, 121, 119, 120, 122, // 4752-4759
124, 127, 130, 132, 134, 134, 133, 132, // 4760-4767
130, 126, 124, 121, 119, 119, 121, 124, // 4768-4775
127, 129, 132, 133, 134, 133, 132, 129, // 4776-4783
127, 125, 122, 120, 119, 121, 123, 126, // 4784-4791
129, 131, 134, 134, 134, 133, 131, 128, // 4792-4799
125, 123, 120, 119, 119, 122, 124, 127, // 4800-4807
130, 132, 134, 134, 133, 132, 130, 127, // 4808-4815
124, 121, 120, 120, 121, 123, 126, 128, // 4816-4823
131, 133, 133, 134, 133, 131, 128, 125, // 4824-4831
122, 121, 119, 120, 122, 124, 127, 130, // 4832-4839
132, 134, 134, 134, 131, 129, 126, 123, // 4840-4847
122, 120, 120, 121, 124, 126, 129, 131, // 4848-4855
133, 134, 133, 132, 129, 127, 124, 121, // 4856-4863
120, 120, 121, 124, 126, 129, 132, 133, // 4864-4871
133, 133, 132, 130, 127, 124, 122, 121, // 4872-4879
121, 122, 123, 126, 129, 131, 132, 133, // 4880-4887
133, 131, 129, 127, 125, 123, 121, 121, // 4888-4895
122, 124, 126, 129, 130, 131, 133, 132, // 4896-4903
132, 130, 127, 125, 124, 121, 120, 121, // 4904-4911
123, 126, 128, 129, 132, 133, 132, 131, // 4912-4919
130, 128, 126, 123, 122, 121, 122, 123, // 4920-4927
125, 128, 130, 132, 132, 133, 132, 130, // 4928-4935
128, 126, 124, 122, 121, 122, 123, 125, // 4936-4943
128, 129, 131, 132, 132, 131, 130, 129, // 4944-4951
127, 124, 123, 122, 122, 124, 125, 127, // 4952-4959
129, 131, 132, 132, 131, 130, 129, 127, // 4960-4967
124, 123, 122, 122, 122, 124, 127, 128, // 4968-4975
130, 131, 132, 131, 130, 130, 127, 125, // 4976-4983
124, 122, 122, 122, 123, 125, 128, 129, // 4984-4991
131, 132, 132, 131, 130, 129, 127, 125, // 4992-4999
123, 122, 122, 124, 125, 127, 129, 130, // 5000-5007
131, 132, 131, 130, 129, 127, 126, 123, // 5008-5015
122, 122, 123, 125, 127, 128, 130, 131, // 5016-5023
132, 131, 130, 130, 127, 125, 124, 122, // 5024-5031
122, 123, 124, 126, 128, 130, 131, 131, // 5032-5039
132, 131, 129, 128, 127, 125, 123, 122, // 5040-5047
123, 124, 126, 128, 129, 130, 131, 131, // 5048-5055
130, 129, 129, 127, 125, 124, 123, 124, // 5056-5063
124, 126, 127, 128, 129, 130, 131, 130, // 5064-5071
129, 128, 127, 125, 124, 123, 123, 124, // 5072-5079
126, 127, 128, 130, 130, 131, 130, 129, // 5080-5087
129, 127, 126, 124, 124, 123, 124, 125, // 5088-5095
126, 128, 129, 130, 130, 130, 130, 128, // 5096-5103
128, 126, 125, 124, 123, 124, 125, 127, // 5104-5111
127, 129, 130, 130, 131, 130, 129, 128, // 5112-5119
127, 125, 123, 123, 123, 124, 126, 127, // 5120-5127
128, 130, 130, 130, 130, 129, 128, 127, // 5128-5135
125, 124, 124, 123, 125, 126, 127, 128, // 5136-5143
129, 130, 130, 130, 129, 128, 128, 126, // 5144-5151
124, 124, 124, 124, 125, 126, 128, 128, // 5152-5159
129, 130, 130, 130, 129, 128, 126, 125, // 5160-5167
124, 124, 124, 124, 126, 128, 128, 129, // 5168-5175
130, 131, 130, 129, 128, 126, 125, 124, // 5176-5183
123, 123, 124, 125, 127, 128, 129, 130, // 5184-5191
130, 129, 130, 128, 128, 126, 125, 124, // 5192-5199
124, 124, 125, 127, 128, 129, 129, 130, // 5200-5207
129, 129, 129, 127, 126, 125, 124, 124, // 5208-5215
125, 126, 126, 128, 129, 129, 130, 130, // 5216-5223
129, 128, 127, 126, 125, 125, 124, 124, // 5224-5231
125, 126, 127, 128, 129, 130, 130, 130, // 5232-5239
129, 128, 127, 125, 124, 123, 124, 124, // 5240-5247
126, 127, 128, 129, 130, 131, 130, 130, // 5248-5255
129, 127, 126, 125, 123, 123, 124, 125, // 5256-5263
126, 128, 129, 130, 131, 131, 130, 129, // 5264-5271
127, 126, 125, 124, 123, 124, 124, 126, // 5272-5279
127, 129, 129, 130, 130, 130, 129, 128, // 5280-5287
127, 126, 125, 124, 124, 124, 126, 127, // 5288-5295
127, 129, 129, 130, 129, 130, 129, 127, // 5296-5303
126, 125, 124, 124, 124, 125, 126, 127, // 5304-5311
128, 129, 130, 130, 130, 129, 128, 127, // 5312-5319
125, 125, 124, 123, 124, 125, 127, 128, // 5320-5327
129, 130, 130, 130, 129, 128, 127, 125, // 5328-5335
124, 124, 124, 124, 126, 127, 128, 129, // 5336-5343
130, 130, 130, 130, 129, 127, 125, 124, // 5344-5351
123, 123, 124, 125, 126, 128, 129, 130, // 5352-5359
130, 131, 129, 129, 128, 126, 125, 123, // 5360-5367
123, 124, 125, 126, 128, 129, 130, 131, // 5368-5375
131, 130, 130, 128, 126, 124, 124, 123, // 5376-5383
123, 124, 125, 127, 128, 129, 131, 131, // 5384-5391
131, 130, 128, 127, 125, 124, 123, 123, // 5392-5399
123, 125, 127, 128, 129, 130, 131, 130, // 5400-5407
130, 128, 127, 126, 123, 123, 123, 124, // 5408-5415
124, 126, 128, 129, 130, 131, 131, 130, // 5416-5423
129, 127, 126, 124, 123, 122, 123, 124, // 5424-5431
126, 127, 129, 130, 131, 132, 131, 129, // 5432-5439
128, 127, 124, 123, 123, 122, 123, 125, // 5440-5447
127, 129, 130, 131, 131, 131, 130, 129, // 5448-5455
127, 125, 124, 123, 123, 124, 124, 126, // 5456-5463
128, 129, 130, 131, 131, 130, 129, 128, // 5464-5471
126, 125, 123, 123, 123, 125, 125, 127, // 5472-5479
129, 130, 131, 131, 131, 130, 128, 127, // 5480-5487
124, 123, 122, 123, 124, 125, 127, 128, // 5488-5495
130, 130, 131, 131, 130, 129, 127, 126, // 5496-5503
124, 123, 122, 124, 125, 126, 128, 129, // 5504-5511
130, 131, 131, 130, 130, 128, 126, 125, // 5512-5519
123, 123, 123, 124, 126, 127, 128, 130, // 5520-5527
131, 131, 131, 130, 128, 127, 126, 124, // 5528-5535
123, 124, 124, 125, 126, 128, 129, 130, // 5536-5543
131, 131, 130, 129, 128, 126, 125, 124, // 5544-5551
124, 124, 125, 126, 127, 128, 129, 130, // 5552-5559
130, 130, 130, 128, 126, 125, 124, 124, // 5560-5567
124, 125, 126, 127, 128, 129, 130, 131, // 5568-5575
130, 130, 128, 127, 125, 125, 124, 124, // 5576-5583
124, 126, 126, 128, 128, 130, 130, 130, // 5584-5591
129, 128, 127, 126, 125, 124, 125, 125, // 5592-5599
125, 126, 127, 128, 129, 130, 130, 130, // 5600-5607
129, 127, 126, 125, 125, 124, 124, 125, // 5608-5615
126, 127, 128, 129, 129, 130, 129, 129, // 5616-5623
128, 126, 125, 125, 124, 125, 125, 126, // 5624-5631
127, 127, 128, 129, 130, 130, 129, 128, // 5632-5639
127, 126, 125, 125, 125, 125, 125, 127, // 5640-5647
127, 128, 128, 129, 129, 130, 128, 127, // 5648-5655
126, 125, 125, 124, 126, 126, 127, 128, // 5656-5663
128, 128, 129, 129, 129, 129, 127, 126, // 5664-5671
125, 124, 125, 125, 126, 127, 127, 128, // 5672-5679
129, 129, 130, 129, 128, 127, 126, 125, // 5680-5687
125, 125, 125, 125, 127, 127, 127, 128, // 5688-5695
128, 129, 129, 128, 127, 127, 126, 125, // 5696-5703
125, 125, 125, 126, 127, 127, 128, 128, // 5704-5711
129, 129, 129, 128, 127, 127, 126, 126, // 5712-5719
125, 126, 125, 126, 126, 127, 127, 128, // 5720-5727
128, 129, 128, 128, 127, 127, 125, 126, // 5728-5735
126, 126, 126, 127, 127, 128, 128, 129, // 5736-5743
129, 128, 127, 127, 126, 126, 126, 126, // 5744-5751
126, 126, 127, 127, 127, 127, 128, 128, // 5752-5759
127, 127, 127, 127, 126, 126, 126, 127, // 5760-5767
126, 127, 127, 128, 128, 128, 128, 128, // 5768-5775
128, 127, 127, 127, 126, 126, 126, 127, // 5776-5783
127, 127, 127, 128, 128, 128, 128, 128, // 5784-5791
127, 126, 126, 126, 126, 126, 126, 127, // 5792-5799
127, 127, 128, 128, 128, 128, 128, 127, // 5800-5807
127, 126, 125, 125, 126, 126, 126, 127, // 5808-5815
127, 127, 128, 129, 129, 128, 128, 127, // 5816-5823
127, 126, 126, 126, 126, 127, 127, 128, // 5824-5831
128, 128, 128, 128, 128, 128, 127, 127, // 5832-5839
126, 125, 126, 126, 126, 127, 128, 128, // 5840-5847
128, 128, 129, 128, 128, 128, 126, 126, // 5848-5855
126, 126, 126, 126, 126, 127, 127, 128, // 5856-5863
129, 129, 129, 128, 128, 126, 126, 125, // 5864-5871
125, 125, 126, 127, 127, 128, 128, 128, // 5872-5879
129, 128, 128, 128, 127, 125, 125, 125, // 5880-5887
125, 126, 126, 128, 128, 128, 129, 129, // 5888-5895
129, 129, 128, 127, 126, 125, 125, 125, // 5896-5903
125, 126, 128, 128, 129, 128, 128, 128, // 5904-5911
128, 127, 127, 126, 126, 125, 125, 126, // 5912-5919
127, 127, 128, 128, 128, 129, 129, 129, // 5920-5927
128, 127, 126, 126, 125, 125, 125, 126, // 5928-5935
127, 128, 127, 129, 128, 128, 128, 128, // 5936-5943
127, 127, 126, 126, 125, 126, 126, 126, // 5944-5951
127, 127, 128, 129, 129, 129, 128, 127, // 5952-5959
127, 126, 125, 125, 126, 126, 127, 127, // 5960-5967
127, 128, 128, 128, 129, 129, 128, 127, // 5968-5975
126, 125, 125, 125, 125, 126, 128, 128, // 5976-5983
128, 128, 129, 128, 128, 127, 127, 126, // 5984-5991
125, 125, 125, 126, 127, 127, 128, 128, // 5992-5999
129, 128, 129, 128, 128, 126, 126, 126, // 6000-6007
125, 125, 125, 126, 127, 128, 128, 129, // 6008-6015
129, 128, 128, 127, 127, 126, 126, 125, // 6016-6023
126, 126, 127, 128, 128, 128, 128, 128, // 6024-6031
128, 128, 128, 127, 126, 126, 125, 126, // 6032-6039
126, 126, 127, 127, 128, 128, 128, 128, // 6040-6047
128, 127, 128, 127, 126, 126, 125, 126, // 6048-6055
127, 126, 127, 127, 128, 128, 128, 128, // 6056-6063
128, 127, 127, 128, 127, 126, 127, 126, // 6064-6071
127, 126, 127, 127, 127, 127, 128, 128, // 6072-6079
128, 128, 128, 127, 126, 126, 127, 126, // 6080-6087
127, 127, 127, 127, 128, 128, 128, 129, // 6088-6095
128, 128, 126, 127, 126, 126, 126, 126, // 6096-6103
127, 126, 128, 128, 128, 129, 129, 128, // 6104-6111
128, 127, 126, 126, 126, 125, 126, 126, // 6112-6119
127, 127, 127, 128, 128, 128, 129, 128, // 6120-6127
127, 126, 126, 126, 126, 126, 126, 126, // 6128-6135
127, 127, 128, 128, 129, 128, 127, 128, // 6136-6143
127, 127, 126, 126, 126, 126, 127, 127, // 6144-6151
127, 128, 127, 128, 128, 128, 128, 127, // 6152-6159
127, 127, 126, 126, 127, 127, 127, 127, // 6160-6167
127, 128, 128, 128, 128, 128, 127, 127, // 6168-6175
126, 126, 127, 126, 127, 126, 127, 127, // 6176-6183
127, 128, 128, 128, 128, 127, 127, 127, // 6184-6191
126, 126, 126, 126, 126, 127, 127, 127, // 6192-6199
127, 128, 128, 128, 128, 127, 127, 126, // 6200-6207
127, 126, 126, 126, 127, 126, 127, 128, // 6208-6215
128, 128, 128, 128, 127, 127, 127, 126, // 6216-6223
126, 126, 127, 126, 127, 127, 127, 128, // 6224-6231
128, 128, 128, 127, 127, 126, 127, 126, // 6232-6239
126, 126, 126, 127, 127, 127, 128, 128, // 6240-6247
128, 128, 128, 128, 127, 126, 126, 126, // 6248-6255
126, 126, 126, 127, 127, 127, 127, 128, // 6256-6263
128, 128, 128, 127, 126, 127, 126, 126, // 6264-6271
126, 126, 126, 126, 127, 128, 128, 128, // 6272-6279
128, 128, 127, 127, 126, 126, 126, 126, // 6280-6287
126, 127, 126, 127, 127, 128, 128, 128, // 6288-6295
128, 127, 127, 127, 127, 126, 126, 127, // 6296-6303
127, 127, 127, 127, 127, 128, 128, 128, // 6304-6311
127, 127, 127, 127, 127, 127, 127, 127, // 6312-6319
127, 127, 127, 128, 127, 128, 128, 128, // 6320-6327
127, 127, 127, 127, 126, 126, 127, 127, // 6328-6335
126, 127, 127, 128, 127, 128, 128, 127, // 6336-6343
127, 127, 127, 126, 126, 127, 127, 126, // 6344-6351
126, 127, 128, 128, 128, 128, 127, 127, // 6352-6359
127, 126, 127, 126, 127, 126, 126, 127, // 6360-6367
126, 127, 128, 128, 128, 128, 128, 128, // 6368-6375
127, 126, 127, 127, 127, 127, 127, 127, // 6376-6383
127, 127, 128, 128, 128, 127, 127, 127, // 6384-6391
127, 126, 126, 127, 127, 126, 126, 127, // 6392-6399
128, 127, 128, 128, 127, 127, 127, 127, // 6400-6407
127, 126, 127, 127, 126, 126, 126, 127, // 6408-6415
128, 128, 128, 127, 128, 127, 127, 127, // 6416-6423
127, 127, 127, 127, 127, 127, 128, 127, // 6424-6431
128, 127, 128, 128, 127, 127, 127, 126, // 6432-6439
126, 127, 127, 126, 126, 127, 128, 128, // 6440-6447
129, 128, 127, 127, 127, 127, 126, 126, // 6448-6455
126, 126, 126, 126, 127, 128, 127, 128, // 6456-6463
128, 128, 128, 127, 127, 127, 126, 126, // 6464-6471
126, 125, 125, 126, 127, 128, 128, 128, // 6472-6479
128, 128, 128, 128, 127, 127, 127, 126, // 6480-6487
125, 126, 125, 126, 127, 128, 128, 128, // 6488-6495
129, 128, 128, 128, 127, 126, 126, 125, // 6496-6503
126, 126, 126, 127, 127, 128, 128, 129, // 6504-6511
129, 128, 128, 128, 126, 127, 125, 126, // 6512-6519
126, 126, 126, 127, 128, 128, 129, 128, // 6520-6527
129, 128, 127, 127, 127, 126, 125, 125, // 6528-6535
126, 126, 127, 128, 128, 128, 129, 128, // 6536-6543
128, 128, 127, 127, 126, 125, 125, 125, // 6544-6551
126, 127, 127, 128, 128, 129, 129, 128, // 6552-6559
127, 128, 126, 126, 126, 125, 126, 126, // 6560-6567
126, 127, 127, 128, 128, 128, 129, 128, // 6568-6575
127, 126, 126, 126, 125, 125, 126, 127, // 6576-6583
127, 128, 128, 128, 128, 128, 128, 127, // 6584-6591
127, 127, 126, 125, 125, 126, 126, 127, // 6592-6599
128, 128, 128, 128, 128, 127, 128, 127, // 6600-6607
126, 127, 126, 126, 126, 126, 127, 127, // 6608-6615
127, 127, 128, 127, 128, 127, 128, 127, // 6616-6623
127, 127, 126, 126, 127, 126, 127, 127, // 6624-6631
127, 127, 127, 127, 128, 127, 127, 127, // 6632-6639
127, 126, 126, 126, 127, 126, 126, 127, // 6640-6647
127, 128, 128, 128, 128, 127, 127, 127, // 6648-6655
127, 127, 126, 126, 127, 127, 127, 127, // 6656-6663
128, 128, 128, 128, 128, 127, 127, 127, // 6664-6671
126, 126, 126, 127, 127, 127, 128, 128, // 6672-6679
127, 128, 128, 128, 128, 127, 127, 126, // 6680-6687
126, 125, 126, 127, 127, 127, 127, 128, // 6688-6695
128, 128, 128, 127, 127, 127, 126, 126, // 6696-6703
126, 126, 126, 126, 127, 127, 128, 128, // 6704-6711
128, 128, 127, 127, 127, 126, 126, 126, // 6712-6719
126, 126, 127, 127, 127, 128, 128, 129, // 6720-6727
128, 128, 128, 127, 126, 126, 125, 126, // 6728-6735
126, 127, 127, 127, 128, 128, 128, 129, // 6736-6743
128, 127, 127, 126, 126, 126, 125, 126, // 6744-6751
126, 127, 127, 128, 127, 128, 128, 127, // 6752-6759
127, 127, 127, 126, 126, 126, 127, 126, // 6760-6767
127, 127, 127, 128, 128, 128, 128, 128, // 6768-6775
128, 127, 126, 126, 126, 126, 126, 127, // 6776-6783
127, 127, 128, 128, 128, 128, 128, 128, // 6784-6791
127, 126, 127, 126, 126, 126, 126, 126, // 6792-6799
127, 128, 128, 128, 128, 128, 127, 128, // 6800-6807
126, 127, 126, 126, 126, 126, 127, 127, // 6808-6815
128, 127, 127, 128, 128, 128, 128, 127, // 6816-6823
126, 126, 126, 126, 127, 127, 128, 128, // 6824-6831
127, 127, 127, 128, 128, 127, 128, 127, // 6832-6839
126, 126, 126, 126, 127, 127, 128, 127, // 6840-6847
128, 128, 127, 127, 127, 128, 127, 127, // 6848-6855
127, 126, 126, 126, 127, 127, 127, 128, // 6856-6863
128, 128, 127, 127, 128, 127, 127, 127, // 6864-6871
127, 127, 127, 127, 127, 127, 127, 127, // 6872-6879
128, 128, 128, 128, 128, 127, 126, 126, // 6880-6887
127, 127, 127, 127, 127, 127, 127, 127, // 6888-6895
128, 128, 127, 128, 127, 126, 126, 126, // 6896-6903
126, 126, 127, 127, 127, 128, 128, 127, // 6904-6911
127, 127, 127, 127, 127, 127, 127, 127, // 6912-6919
127, 127, 127, 127, 127, 127, 128, 128, // 6920-6927
128, 127, 127, 127, 127, 126, 126, 127, // 6928-6935
127, 127, 127, 127, 127, 127, 128, 128, // 6936-6943
127, 127, 127, 126, 126, 126, 126, 126, // 6944-6951
127, 127, 127, 127, 127, 128, 128, 127, // 6952-6959
127, 127, 126, 126, 126, 126, 126, 127, // 6960-6967
127, 127, 128, 128, 128, 127, 128, 127, // 6968-6975
127, 126, 126, 126, 126, 127, 127, 127, // 6976-6983
127, 128, 128, 128, 128, 128, 127, 127, // 6984-6991
127, 127, 126, 126, 127, 127, 127, 127, // 6992-6999
127, 128, 128, 128, 128, 127, 127, 127, // 7000-7007
126, 126, 126, 126, 126, 127, 127, 127, // 7008-7015
127, 127, 128, 128, 127, 127, 127, 126, // 7016-7023
126, 126, 126, 126, 127, 127, 127, 128, // 7024-7031
128, 128, 127, 127, 127, 127, 126, 126, // 7032-7039
126, 126, 126, 127, 127, 127, 128, 128, // 7040-7047
128, 128, 128, 127, 127, 127, 126, 126, // 7048-7055
127, 127, 127, 127, 127, 127, 127, 128, // 7056-7063
128, 128, 127, 127, 127, 126, 126, 126, // 7064-7071
126, 127, 127, 127, 127, 127, 127, 127, // 7072-7079
127, 127, 127, 127, 126, 126, 126, 126, // 7080-7087
126, 127, 127, 127, 128, 128, 128, 127, // 7088-7095
128, 127, 127, 127, 127, 126, 127, 127, // 7096-7103
127, 127, 127, 127, 127, 128, 128, 128, // 7104-7111
127, 127, 127, 126, 126, 126, 126, 126, // 7112-7119
127, 127, 127, 128, 127, 127, 127, 127, // 7120-7127
127, 127, 126, 126, 126, 126, 127, 127, // 7128-7135
128, 128, 128, 128, 128, 128, 128, 127, // 7136-7143
127, 126, 126, 126, 126, 127, 127, 128, // 7144-7151
128, 128, 129, 128, 128, 128, 127, 126, // 7152-7159
127, 126, 126, 126, 126, 127, 127, 128, // 7160-7167
127, 128, 128, 127, 127, 127, 127, 126, // 7168-7175
126, 126, 126, 126, 127, 127, 128, 128, // 7176-7183
128, 128, 128, 127, 127, 126, 126, 126, // 7184-7191
126, 126, 127, 127, 127, 128, 128, 128, // 7192-7199
128, 128, 128, 127, 127, 126, 126, 126, // 7200-7207
126, 126, 127, 127, 128, 128, 128, 128, // 7208-7215
127, 128, 127, 127, 126, 126, 126, 126, // 7216-7223
126, 126, 127, 128, 128, 128, 128, 128, // 7224-7231
127, 127, 127, 126, 126, 126, 125, 126, // 7232-7239
126, 128, 128, 128, 128, 128, 128, 128, // 7240-7247
127, 127, 126, 126, 125, 126, 126, 127, // 7248-7255
127, 127, 128, 128, 128, 128, 128, 128, // 7256-7263
126, 126, 126, 125, 126, 126, 126, 127, // 7264-7271
128, 128, 128, 129, 128, 127, 127, 127, // 7272-7279
127, 126, 125, 126, 126, 126, 127, 128, // 7280-7287
128, 128, 129, 128, 128, 127, 127, 126, // 7288-7295
126, 126, 126, 125, 127, 127, 128, 129, // 7296-7303
128, 129, 128, 128, 128, 127, 126, 126, // 7304-7311
126, 125, 126, 126, 127, 127, 128, 128, // 7312-7319
129, 128, 128, 128, 127, 126, 126, 126, // 7320-7327
125, 126, 126, 126, 127, 128, 128, 128, // 7328-7335
129, 128, 127, 127, 126, 125, 126, 125, // 7336-7343
126, 126, 126, 127, 128, 129, 129, 129, // 7344-7351
128, 128, 127, 127, 126, 125, 125, 125, // 7352-7359
125, 126, 127, 128, 129, 129, 129, 128, // 7360-7367
128, 128, 127, 126, 125, 125, 125, 125, // 7368-7375
126, 127, 127, 128, 129, 129, 129, 129, // 7376-7383
128, 127, 126, 125, 125, 125, 126, 126, // 7384-7391
126, 128, 128, 129, 129, 129, 129, 127, // 7392-7399
127, 127, 126, 125, 125, 126, 126, 126, // 7400-7407
128, 128, 129, 129, 129, 128, 128, 127, // 7408-7415
127, 126, 125, 125, 125, 125, 127, 127, // 7416-7423
128, 129, 129, 129, 128, 128, 127, 126, // 7424-7431
126, 125, 125, 125, 126, 126, 127, 128, // 7432-7439
129, 129, 129, 129, 129, 127, 126, 126, // 7440-7447
125, 125, 125, 126, 126, 126, 128, 128, // 7448-7455
129, 129, 129, 129, 127, 127, 127, 125, // 7456-7463
125, 125, 126, 126, 126, 127, 128, 129, // 7464-7471
129, 129, 128, 128, 127, 126, 126, 125, // 7472-7479
125, 125, 125, 127, 127, 127, 129, 129, // 7480-7487
129, 129, 128, 127, 126, 126, 125, 125, // 7488-7495
125, 126, 126, 127, 128, 128, 129, 129, // 7496-7503
129, 128, 127, 127, 126, 125, 126, 125, // 7504-7511
126, 126, 126, 128, 128, 129, 129, 129, // 7512-7519
128, 128, 127, 127, 125, 125, 125, 125, // 7520-7527
126, 127, 128, 128, 129, 129, 129, 128, // 7528-7535
128, 127, 126, 126, 125, 126, 125, 126, // 7536-7543
127, 127, 128, 129, 129, 129, 128, 128, // 7544-7551
127, 126, 126, 125, 125, 125, 125, 126, // 7552-7559
127, 127, 129, 129, 129, 129, 129, 127, // 7560-7567
127, 126, 125, 125, 125, 126, 126, 126, // 7568-7575
127, 128, 129, 129, 129, 128, 128, 127, // 7576-7583
127, 126, 126, 125, 126, 126, 126, 127, // 7584-7591
128, 129, 129, 129, 128, 128, 127, 126, // 7592-7599
126, 125, 125, 126, 125, 127, 127, 128, // 7600-7607
129, 129, 129, 128, 127, 127, 126, 126, // 7608-7615
125, 125, 125, 126, 127, 127, 128, 129, // 7616-7623
129, 129, 128, 127, 127, 126, 126, 125, // 7624-7631
125, 125, 126, 126, 128, 128, 128, 129, // 7632-7639
129, 129, 128, 127, 127, 125, 126, 125, // 7640-7647
125, 126, 126, 127, 128, 128, 129, 129, // 7648-7655
129, 128, 127, 126, 126, 126, 125, 125, // 7656-7663
126, 127, 127, 127, 129, 128, 129, 129, // 7664-7671
128, 127, 126, 126, 126, 125, 126, 126, // 7672-7679
127, 127, 127, 128, 128, 129, 129, 128, // 7680-7687
127, 127, 127, 126, 126, 125, 126, 126, // 7688-7695
126, 128, 128, 128, 129, 129, 128, 127, // 7696-7703
127, 127, 126, 126, 125, 126, 126, 126, // 7704-7711
127, 127, 129, 128, 129, 128, 128, 128, // 7712-7719
126, 126, 126, 125, 126, 126, 127, 127, // 7720-7727
127, 128, 128, 129, 128, 128, 128, 127, // 7728-7735
126, 125, 126, 126, 126, 127, 127, 128, // 7736-7743
128, 128, 128, 129, 128, 127, 127, 127, // 7744-7751
126, 126, 126, 126, 126, 126, 127, 128, // 7752-7759
129, 128, 129, 128, 127, 127, 126, 126, // 7760-7767
126, 126, 126, 126, 127, 127, 127, 128, // 7768-7775
128, 129, 128, 128, 128, 126, 126, 126, // 7776-7783
126, 126, 126, 127, 127, 127, 128, 128, // 7784-7791
129, 128, 128, 127, 127, 127, 125, 126, // 7792-7799
126, 126, 127, 127, 128, 128, 129, 128, // 7800-7807
129, 128, 127, 127, 127, 126, 126, 126, // 7808-7815
126, 126, 126, 127, 128, 129, 128, 129, // 7816-7823
128, 127, 127, 126, 126, 126, 126, 126, // 7824-7831
126, 126, 127, 127, 128, 128, 128, 128, // 7832-7839
128, 128, 126, 126, 125, 126, 126, 126, // 7840-7847
127, 127, 127, 128, 128, 128, 128, 128, // 7848-7855
128, 127, 126, 125, 126, 126, 126, 126, // 7856-7863
126, 128, 128, 129, 128, 129, 128, 127, // 7864-7871
127, 126, 126, 126, 126, 126, 126, 126, // 7872-7879
127, 128, 129, 128, 129, 128, 127, 127, // 7880-7887
126, 126, 126, 126, 126, 126, 126, 127, // 7888-7895
127, 128, 128, 129, 128, 128, 128, 126, // 7896-7903
126, 125, 126, 125, 126, 127, 127, 127, // 7904-7911
128, 128, 129, 129, 128, 128, 127, 126, // 7912-7919
125, 126, 125, 126, 127, 127, 128, 128, // 7920-7927
129, 128, 129, 128, 127, 127, 126, 126, // 7928-7935
126, 125, 126, 126, 126, 127, 128, 129, // 7936-7943
128, 129, 128, 127, 127, 126, 126, 126, // 7944-7951
125, 126, 126, 127, 127, 127, 129, 128, // 7952-7959
129, 128, 128, 128, 126, 126, 126, 126, // 7960-7967
125, 126, 127, 127, 128, 128, 128, 129, // 7968-7975
129, 128, 127, 127, 127, 125, 126, 125, // 7976-7983
126, 126, 126, 127, 128, 128, 128, 129, // 7984-7991
128, 127, 127, 126, 126, 126, 125, 126, // 7992-7999
126, 127, 127, 127, 128, 128, 129, 128, // 8000-8007
128, 127, 126, 126, 125, 126, 126, 126, // 8008-8015
127, 127, 128, 128, 128, 128, 128, 128, // 8016-8023
127, 127, 126, 125, 126, 126, 126, 127, // 8024-8031
127, 128, 128, 128, 128, 129, 128, 127, // 8032-8039
127, 126, 126, 126, 125, 126, 126, 127, // 8040-8047
127, 128, 129, 129, 129, 128, 127, 127, // 8048-8055
126, 126, 126, 125, 125, 126, 127, 127, // 8056-8063
127, 129, 128, 129, 128, 128, 127, 126, // 8064-8071
126, 125, 126, 125, 126, 127, 127, 128, // 8072-8079
128, 128, 129, 129, 128, 127, 127, 127, // 8080-8087
125, 126, 125, 126, 126, 126, 128, 128, // 8088-8095
128, 129, 129, 128, 127, 127, 126, 126, // 8096-8103
126, 125, 126, 126, 127, 127, 128, 129, // 8104-8111
128, 129, 128, 128, 128, 126, 126, 125, // 8112-8119
126, 125, 126, 127, 127, 127, 128, 128, // 8120-8127
129, 128, 128, 127, 127, 126, 125, 126, // 8128-8135
125, 126, 127, 127, 128, 128, 128, 128, // 8136-8143
128, 128, 127, 127, 126, 126, 126, 126, // 8144-8151
126, 126, 126, 128, 128, 129, 128, 128, // 8152-8159
128, 127, 127, 126, 126, 126, 126, 126, // 8160-8167
126, 127, 127, 127, 128, 128, 128, 128, // 8168-8175
127, 127, 126, 126, 125, 126, 126, 126, // 8176-8183
127, 127, 127, 128, 128, 128, 128, 128, // 8184-8191
127, 127, 127, 126, 126, 126, 126, 127, // 8192-8199
127, 128, 128, 129, 128, 128, 128, 127, // 8200-8207
127, 126, 126, 126, 126, 126, 126, 127, // 8208-8215
127, 127, 128, 128, 128, 128, 127, 127, // 8216-8223
126, 126, 125, 126, 126, 126, 127, 127, // 8224-8231
128, 128, 128, 128, 128, 128, 127, 127, // 8232-8239
125, 126, 126, 126, 126, 127, 127, 128, // 8240-8247
128, 129, 128, 128, 128, 127, 127, 126, // 8248-8255
126, 126, 126, 126, 127, 128, 128, 128, // 8256-8263
129, 128, 128, 128, 127, 126, 126, 126, // 8264-8271
125, 126, 126, 127, 127, 127, 128, 128, // 8272-8279
128, 128, 128, 127, 126, 126, 126, 125, // 8280-8287
126, 126, 127, 127, 127, 128, 128, 128, // 8288-8295
128, 128, 127, 126, 126, 125, 126, 126, // 8296-8303
126, 126, 127, 128, 128, 128, 129, 128, // 8304-8311
128, 127, 127, 127, 126, 126, 126, 126, // 8312-8319
126, 127, 128, 128, 129, 129, 128, 128, // 8320-8327
128, 127, 126, 126, 126, 125, 126, 126, // 8328-8335
127, 128, 128, 129, 128, 128, 128, 128, // 8336-8343
127, 126, 126, 126, 125, 126, 126, 127, // 8344-8351
127, 127, 128, 128, 129, 128, 128, 127, // 8352-8359
126, 126, 125, 126, 126, 126, 126, 127, // 8360-8367
128, 128, 128, 129, 128, 128, 127, 127, // 8368-8375
127, 126, 126, 126, 126, 126, 127, 128, // 8376-8383
128, 128, 129, 128, 128, 128, 127, 126, // 8384-8391
126, 126, 125, 126, 126, 127, 127, 128, // 8392-8399
129, 128, 128, 128, 128, 127, 126, 126, // 8400-8407
125, 125, 126, 126, 126, 127, 127, 128, // 8408-8415
128, 129, 128, 128, 127, 126, 126, 125, // 8416-8423
125, 125, 126, 126, 127, 128, 128, 128, // 8424-8431
129, 128, 128, 128, 127, 127, 125, 126, // 8432-8439
125, 126, 126, 127, 128, 128, 129, 129, // 8440-8447
129, 128, 128, 127, 126, 126, 126, 125, // 8448-8455
126, 126, 127, 128, 128, 129, 129, 129, // 8456-8463
128, 128, 127, 126, 126, 125, 125, 126, // 8464-8471
126, 126, 127, 128, 128, 128, 129, 128, // 8472-8479
128, 127, 126, 126, 125, 125, 125, 126, // 8480-8487
126, 127, 128, 128, 129, 129, 128, 128, // 8488-8495
128, 127, 126, 125, 125, 125, 126, 126, // 8496-8503
127, 128, 128, 129, 129, 129, 128, 128, // 8504-8511
127, 126, 126, 125, 125, 125, 126, 127, // 8512-8519
127, 128, 129, 129, 129, 128, 128, 127, // 8520-8527
126, 126, 125, 125, 125, 126, 126, 127, // 8528-8535
128, 128, 129, 129, 129, 128, 128, 127, // 8536-8543
125, 125, 124, 125, 126, 126, 127, 128, // 8544-8551
128, 129, 129, 129, 128, 128, 127, 126, // 8552-8559
126, 125, 125, 125, 126, 127, 128, 129, // 8560-8567
129, 129, 129, 128, 128, 127, 126, 126, // 8568-8575
125, 125, 125, 126, 126, 127, 128, 129, // 8576-8583
130, 129, 129, 128, 127, 126, 126, 125, // 8584-8591
125, 125, 126, 126, 127, 128, 128, 129, // 8592-8599
129, 129, 128, 128, 127, 125, 125, 124, // 8600-8607
125, 125, 126, 127, 128, 128, 129, 129, // 8608-8615
129, 128, 128, 127, 126, 126, 125, 125, // 8616-8623
125, 126, 127, 128, 129, 129, 130, 129, // 8624-8631
129, 128, 127, 126, 126, 125, 125, 125, // 8632-8639
126, 126, 127, 128, 128, 129, 129, 129, // 8640-8647
128, 127, 126, 126, 125, 124, 125, 126, // 8648-8655
126, 127, 128, 128, 129, 129, 129, 128, // 8656-8663
128, 127, 126, 126, 125, 125, 125, 126, // 8664-8671
127, 128, 129, 129, 130, 129, 129, 128, // 8672-8679
127, 126, 126, 125, 125, 125, 126, 127, // 8680-8687
127, 128, 128, 129, 129, 129, 128, 127, // 8688-8695
126, 125, 125, 124, 125, 125, 126, 127, // 8696-8703
128, 128, 129, 129, 129, 129, 127, 126, // 8704-8711
125, 125, 125, 125, 125, 126, 127, 128, // 8712-8719
128, 129, 129, 129, 129, 129, 127, 127, // 8720-8727
126, 125, 125, 125, 126, 127, 128, 128, // 8728-8735
129, 129, 129, 129, 129, 127, 126, 126, // 8736-8743
125, 124, 125, 125, 127, 127, 128, 128, // 8744-8751
129, 129, 129, 129, 127, 126, 126, 125, // 8752-8759
125, 125, 125, 126, 127, 128, 128, 129, // 8760-8767
129, 129, 129, 127, 127, 126, 126, 125, // 8768-8775
125, 125, 126, 127, 128, 129, 129, 129, // 8776-8783
129, 129, 127, 127, 126, 126, 125, 126, // 8784-8791
125, 126, 127, 128, 128, 128, 129, 129, // 8792-8799
129, 128, 127, 126, 126, 125, 126, 125, // 8800-8807
125, 127, 127, 128, 128, 129, 128, 129, // 8808-8815
129, 127, 126, 127, 126, 125, 125, 125, // 8816-8823
127, 127, 128, 128, 129, 128, 129, 129, // 8824-8831
127, 127, 127, 126, 125, 126, 125, 126, // 8832-8839
127, 128, 127, 128, 129, 129, 129, 128, // 8840-8847
127, 127, 126, 125, 126, 125, 125, 127, // 8848-8855
127, 127, 128, 129, 128, 129, 129, 128, // 8856-8863
127, 126, 126, 125, 126, 125, 127, 127, // 8864-8871
127, 128, 129, 128, 129, 129, 128, 128, // 8872-8879
127, 126, 125, 126, 125, 126, 127, 128, // 8880-8887
128, 128, 129, 128, 129, 128, 128, 127, // 8888-8895
126, 125, 126, 125, 126, 127, 128, 127, // 8896-8903
128, 129, 128, 129, 128, 128, 127, 126, // 8904-8911
126, 125, 126, 126, 127, 127, 128, 128, // 8912-8919
129, 128, 129, 128, 128, 127, 127, 126, // 8920-8927
125, 126, 125, 127, 127, 128, 128, 129, // 8928-8935
128, 129, 129, 128, 128, 127, 126, 125, // 8936-8943
126, 125, 126, 127, 128, 128, 128, 129, // 8944-8951
129, 129, 128, 128, 127, 126, 125, 125, // 8952-8959
125, 126, 127, 128, 127, 128, 129, 128, // 8960-8967
129, 128, 128, 127, 126, 125, 125, 125, // 8968-8975
125, 126, 128, 128, 128, 129, 129, 129, // 8976-8983
128, 128, 127, 126, 126, 125, 124, 125, // 8984-8991
126, 127, 128, 128, 129, 129, 129, 128, // 8992-8999
128, 126, 126, 126, 125, 125, 125, 126, // 9000-9007
127, 128, 129, 129, 129, 128, 128, 128, // 9008-9015
127, 126, 126, 125, 125, 125, 126, 127, // 9016-9023
128, 129, 128, 129, 128, 129, 128, 127, // 9024-9031
126, 125, 125, 125, 125, 125, 126, 128, // 9032-9039
128, 128, 129, 129, 129, 128, 128, 126, // 9040-9047
126, 126, 125, 125, 125, 126, 127, 128, // 9048-9055
128, 129, 129, 129, 128, 128, 127, 127, // 9056-9063
126, 125, 125, 125, 126, 126, 128, 128, // 9064-9071
129, 129, 128, 128, 128, 128, 127, 126, // 9072-9079
125, 125, 125, 126, 126, 128, 128, 128, // 9080-9087
129, 128, 128, 128, 128, 127, 126, 125, // 9088-9095
125, 126, 126, 126, 128, 128, 128, 129, // 9096-9103
129, 128, 128, 128, 127, 126, 126, 125, // 9104-9111
125, 126, 126, 127, 128, 128, 129, 129, // 9112-9119
128, 128, 128, 127, 127, 126, 125, 125, // 9120-9127
126, 126, 127, 128, 129, 128, 129, 128, // 9128-9135
128, 128, 128, 127, 126, 125, 125, 126, // 9136-9143
126, 126, 128, 128, 128, 129, 129, 128, // 9144-9151
128, 128, 127, 126, 126, 125, 125, 126, // 9152-9159
126, 126, 127, 128, 129, 129, 128, 128, // 9160-9167
128, 127, 127, 126, 125, 125, 126, 126, // 9168-9175
126, 127, 128, 129, 129, 128, 128, 128, // 9176-9183
127, 127, 126, 125, 125, 126, 126, 126, // 9184-9191
128, 128, 128, 129, 129, 128, 128, 128, // 9192-9199
127, 126, 125, 125, 125, 126, 126, 127, // 9200-9207
128, 128, 129, 129, 128, 128, 128, 127, // 9208-9215
126, 126, 125, 125, 126, 126, 126, 128, // 9216-9223
128, 129, 129, 129, 128, 128, 127, 127, // 9224-9231
126, 125, 125, 125, 126, 126, 127, 128, // 9232-9239
129, 129, 129, 128, 128, 128, 127, 126, // 9240-9247
125, 125, 124, 126, 126, 127, 128, 128, // 9248-9255
129, 129, 128, 128, 128, 127, 126, 125, // 9256-9263
125, 125, 126, 126, 127, 127, 128, 129, // 9264-9271
129, 129, 128, 128, 127, 126, 126, 125, // 9272-9279
125, 125, 126, 126, 127, 128, 129, 129, // 9280-9287
129, 128, 128, 127, 127, 126, 125, 125, // 9288-9295
125, 126, 126, 127, 128, 128, 129, 129, // 9296-9303
128, 128, 128, 127, 126, 125, 125, 125, // 9304-9311
126, 126, 127, 127, 128, 129, 129, 129, // 9312-9319
128, 128, 127, 126, 126, 125, 125, 126, // 9320-9327
126, 127, 127, 128, 129, 129, 129, 128, // 9328-9335
128, 127, 126, 126, 125, 125, 125, 126, // 9336-9343
126, 127, 128, 129, 129, 129, 128, 128, // 9344-9351
127, 127, 126, 125, 125, 125, 126, 126, // 9352-9359
127, 128, 129, 129, 129, 128, 128, 128, // 9360-9367
127, 126, 125, 125, 124, 126, 126, 127, // 9368-9375
128, 128, 129, 129, 128, 128, 128, 127, // 9376-9383
126, 125, 125, 125, 126, 126, 126, 127, // 9384-9391
128, 129, 129, 129, 128, 128, 127, 127, // 9392-9399
126, 125, 125, 125, 126, 126, 127, 128, // 9400-9407
129, 129, 129, 128, 128, 127, 127, 126, // 9408-9415
125, 125, 125, 126, 126, 127, 128, 128, // 9416-9423
129, 129, 129, 128, 128, 127, 126, 125, // 9424-9431
125, 125, 125, 126, 127, 127, 128, 129, // 9432-9439
129, 129, 128, 128, 127, 126, 126, 125, // 9440-9447
125, 125, 126, 126, 127, 128, 129, 129, // 9448-9455
129, 128, 128, 127, 127, 126, 125, 125, // 9456-9463
125, 126, 126, 127, 128, 128, 129, 129, // 9464-9471
129, 128, 128, 127, 126, 125, 125, 125, // 9472-9479
126, 126, 127, 128, 128, 129, 129, 129, // 9480-9487
128, 128, 127, 126, 126, 125, 125, 126, // 9488-9495
126, 127, 127, 128, 129, 129, 129, 128, // 9496-9503
128, 127, 126, 126, 125, 125, 125, 126, // 9504-9511
126, 127, 128, 129, 129, 129, 128, 128, // 9512-9519
127, 127, 126, 125, 125, 125, 126, 126, // 9520-9527
127, 128, 128, 129, 129, 128, 128, 128, // 9528-9535
127, 126, 125, 125, 125, 126, 126, 127, // 9536-9543
128, 128, 129, 129, 129, 128, 128, 127, // 9544-9551
126, 126, 125, 125, 125, 126, 127, 127, // 9552-9559
128, 129, 129, 129, 128, 128, 127, 126, // 9560-9567
126, 125, 125, 125, 126, 127, 127, 128, // 9568-9575
129, 129, 129, 128, 128, 127, 127, 126, // 9576-9583
125, 125, 125, 126, 126, 127, 128, 128, // 9584-9591
129, 129, 128, 128, 127, 127, 126, 125, // 9592-9599
125, 125, 126, 126, 127, 127, 128, 129, // 9600-9607
129, 129, 128, 128, 127, 126, 126, 125, // 9608-9615
125, 125, 126, 127, 127, 128, 129, 129, // 9616-9623
129, 128, 128, 127, 127, 126, 125, 125, // 9624-9631
125, 126, 126, 127, 128, 128, 129, 129, // 9632-9639
128, 128, 127, 127, 126, 125, 125, 125, // 9640-9647
126, 126, 127, 128, 128, 129, 129, 129, // 9648-9655
128, 128, 127, 126, 126, 125, 125, 125, // 9656-9663
126, 127, 127, 128, 129, 129, 129, 128, // 9664-9671
128, 127, 126, 126, 125, 125, 125, 126, // 9672-9679
127, 127, 128, 128, 129, 129, 129, 128, // 9680-9687
127, 127, 126, 125, 125, 125, 126, 126, // 9688-9695
127, 128, 128, 129, 129, 129, 128, 127, // 9696-9703
127, 126, 126, 125, 125, 125, 126, 127, // 9704-9711
127, 128, 129, 129, 129, 128, 128, 127, // 9712-9719
126, 126, 125, 125, 125, 126, 127, 127, // 9720-9727
128, 128, 129, 129, 129, 128, 127, 127, // 9728-9735
126, 125, 125, 125, 125, 127, 127, 128, // 9736-9743
128, 129, 129, 129, 129, 127, 127, 126, // 9744-9751
126, 125, 125, 125, 126, 127, 128, 128, // 9752-9759
129, 129, 129, 129, 127, 127, 126, 126, // 9760-9767
125, 125, 125, 126, 127, 127, 128, 129, // 9768-9775
129, 129, 129, 128, 127, 126, 126, 125, // 9776-9783
125, 125, 125, 127, 127, 128, 128, 129, // 9784-9791
129, 129, 128, 127, 127, 126, 125, 125, // 9792-9799
125, 125, 126, 127, 128, 128, 129, 129, // 9800-9807
129, 129, 127, 127, 126, 126, 125, 125, // 9808-9815
125, 126, 127, 128, 128, 129, 129, 129, // 9816-9823
129, 127, 127, 126, 126, 125, 125, 125, // 9824-9831
125, 127, 127, 128, 129, 129, 129, 129, // 9832-9839
129, 127, 126, 126, 125, 125, 125, 125, // 9840-9847
127, 127, 128, 128, 129, 129, 129, 129, // 9848-9855
127, 127, 126, 125, 125, 125, 125, 126, // 9856-9863
127, 128, 128, 129, 129, 129, 129, 127, // 9864-9871
127, 126, 126, 125, 125, 125, 125, 127, // 9872-9879
128, 128, 129, 129, 129, 129, 128, 127, // 9880-9887
126, 126, 125, 125, 125, 125, 127, 127, // 9888-9895
128, 128, 129, 129, 129, 129, 127, 126, // 9896-9903
126, 125, 125, 125, 125, 127, 127, 128, // 9904-9911
128, 129, 129, 129, 129, 127, 127, 126, // 9912-9919
125, 125, 125, 125, 126, 127, 128, 128, // 9920-9927
129, 129, 129, 129, 128, 127, 126, 126, // 9928-9935
125, 125, 125, 125, 127, 128, 128, 129, // 9936-9943
129, 129, 129, 128, 128, 126, 126, 125, // 9944-9951
125, 125, 125, 126, 128, 128, 129, 129, // 9952-9959
129, 129, 128, 128, 126, 126, 125, 125, // 9960-9967
125, 125, 126, 127, 128, 129, 129, 129, // 9968-9975
129, 129, 128, 126, 126, 125, 125, 125, // 9976-9983
125, 126, 127, 128, 128, 129, 129, 129, // 9984-9991
129, 128, 127, 126, 125, 125, 125, 125, // 9992-9999
126, 127, 128, 128, 129, 129, 129, 129, // 10000-10007
128, 127, 126, 126, 125, 125, 125, 125, // 10008-10015
126, 128, 128, 129, 129, 129, 129, 128, // 10016-10023
128, 126, 126, 125, 125, 125, 125, 126, // 10024-10031
127, 128, 128, 129, 129, 129, 128, 128, // 10032-10039
126, 126, 125, 125, 125, 125, 126, 127, // 10040-10047
128, 128, 129, 129, 129, 129, 128, 127, // 10048-10055
126, 126, 125, 125, 125, 125, 126, 128, // 10056-10063
128, 129, 129, 129, 129, 128, 128, 126, // 10064-10071
126, 125, 125, 125, 125, 126, 127, 128, // 10072-10079
128, 129, 129, 129, 128, 128, 126, 126, // 10080-10087
125, 125, 125, 125, 126, 127, 128, 128, // 10088-10095
129, 129, 129, 129, 128, 127, 126, 126, // 10096-10103
125, 125, 125, 126, 127, 128, 128, 129, // 10104-10111
129, 129, 129, 128, 127, 126, 126, 125, // 10112-10119
125, 125, 125, 126, 127, 128, 129, 129, // 10120-10127
129, 129, 128, 128, 126, 126, 125, 125, // 10128-10135
125, 125, 126, 127, 128, 128, 129, 129, // 10136-10143
129, 129, 128, 127, 126, 125, 125, 125, // 10144-10151
125, 126, 126, 128, 128, 129, 129, 129, // 10152-10159
129, 128, 128, 126, 126, 125, 125, 125, // 10160-10167
125, 126, 128, 128, 129, 129, 129, 129, // 10168-10175
128, 128, 126, 126, 125, 125, 125, 125, // 10176-10183
126, 127, 128, 128, 129, 129, 129, 129, // 10184-10191
128, 126, 126, 125, 125, 125, 125, 126, // 10192-10199
126, 128, 128, 129, 129, 129, 129, 128, // 10200-10207
127, 126, 125, 125, 125, 125, 126, 126, // 10208-10215
128, 128, 129, 129, 129, 129, 128, 128, // 10216-10223
126, 126, 125, 125, 125, 125, 126, 128, // 10224-10231
128, 129, 129, 129, 129, 128, 128, 126, // 10232-10239
126, 125, 125, 125, 125, 126, 126, 128, // 10240-10247
129, 129, 129, 129, 129, 128, 127, 126, // 10248-10255
125, 125, 125, 125, 126, 126, 128, 128, // 10256-10263
129, 129, 129, 129, 128, 128, 126, 125, // 10264-10271
125, 125, 125, 125, 126, 128, 128, 129, // 10272-10279
129, 129, 129, 128, 128, 126, 126, 125, // 10280-10287
125, 125, 125, 126, 126, 128, 129, 129, // 10288-10295
129, 129, 129, 128, 126, 126, 125, 125, // 10296-10303
125, 125, 126, 126, 128, 129, 129, 129, // 10304-10311
129, 129, 128, 126, 126, 125, 125, 125, // 10312-10319
125, 126, 126, 128, 128, 129, 129, 129, // 10320-10327
129, 128, 128, 126, 125, 125, 125, 125, // 10328-10335
125, 126, 128, 128, 129, 129, 129, 129, // 10336-10343
128, 128, 126, 126, 125, 125, 125, 125, // 10344-10351
126, 127, 128, 129, 129, 129, 129, 129, // 10352-10359
128, 126, 126, 125, 125, 125, 125, 126, // 10360-10367
126, 128, 129, 129, 129, 129, 129, 128, // 10368-10375
127, 126, 125, 125, 125, 125, 126, 126, // 10376-10383
128, 128, 129, 129, 129, 129, 128, 128, // 10384-10391
126, 125, 125, 125, 125, 125, 126, 127, // 10392-10399
128, 129, 129, 129, 129, 128, 128, 126, // 10400-10407
126, 125, 125, 125, 125, 126, 126, 128, // 10408-10415
129, 129, 129, 129, 128, 128, 127, 126, // 10416-10423
125, 125, 125, 125, 126, 126, 128, 128, // 10424-10431
129, 129, 129, 129, 128, 127, 126, 125, // 10432-10439
125, 125, 125, 126, 126, 128, 128, 129, // 10440-10447
129, 129, 129, 128, 128, 126, 126, 125, // 10448-10455
125, 125, 126, 126, 127, 128, 129, 129, // 10456-10463
129, 129, 128, 128, 127, 126, 125, 125, // 10464-10471
125, 125, 126, 127, 127, 129, 129, 129, // 10472-10479
129, 128, 128, 127, 126, 125, 125, 125, // 10480-10487
125, 126, 126, 127, 128, 129, 129, 129, // 10488-10495
128, 128, 127, 127, 126, 125, 125, 125, // 10496-10503
126, 126, 127, 128, 129, 129, 129, 128, // 10504-10511
128, 128, 127, 126, 125, 125, 125, 126, // 10512-10519
126, 127, 128, 129, 129, 129, 129, 128, // 10520-10527
128, 127, 126, 125, 125, 125, 126, 126, // 10528-10535
126, 128, 128, 129, 129, 129, 128, 128, // 10536-10543
127, 126, 126, 125, 125, 125, 126, 126, // 10544-10551
127, 128, 129, 129, 129, 128, 128, 127, // 10552-10559
127, 126, 125, 125, 125, 126, 126, 127, // 10560-10567
128, 128, 129, 129, 128, 128, 128, 127, // 10568-10575
126, 125, 125, 125, 126, 126, 127, 128, // 10576-10583
128, 129, 129, 128, 128, 128, 127, 126, // 10584-10591
126, 125, 125, 126, 126, 126, 128, 128, // 10592-10599
129, 129, 129, 128, 128, 127, 126, 126, // 10600-10607
125, 125, 125, 126, 126, 127, 128, 129, // 10608-10615
129, 129, 128, 128, 128, 127, 126, 125, // 10616-10623
125, 125, 126, 126, 127, 128, 128, 129, // 10624-10631
129, 128, 128, 128, 127, 126, 125, 125, // 10632-10639
125, 126, 126, 127, 128, 128, 129, 129, // 10640-10647
128, 128, 128, 127, 126, 126, 125, 125, // 10648-10655
126, 126, 126, 127, 128, 129, 129, 128, // 10656-10663
128, 128, 127, 127, 126, 125, 125, 126, // 10664-10671
126, 126, 127, 128, 128, 129, 128, 128, // 10672-10679
128, 127, 127, 126, 125, 125, 126, 126, // 10680-10687
126, 127, 127, 128, 129, 129, 128, 128, // 10688-10695
128, 127, 126, 126, 125, 125, 126, 126, // 10696-10703
127, 127, 128, 129, 129, 128, 128, 128, // 10704-10711
127, 127, 126, 125, 125, 126, 126, 126, // 10712-10719
127, 128, 128, 129, 128, 128, 128, 127, // 10720-10727
127, 126, 125, 125, 126, 126, 126, 127, // 10728-10735
127, 128, 128, 128, 128, 128, 127, 127, // 10736-10743
126, 126, 125, 126, 126, 126, 127, 127, // 10744-10751
128, 128, 128, 128, 128, 128, 127, 127, // 10752-10759
126, 125, 126, 126, 126, 127, 127, 128, // 10760-10767
128, 128, 128, 128, 128, 127, 127, 126, // 10768-10775
126, 126, 126, 126, 126, 127, 127, 128, // 10776-10783
128, 128, 128, 128, 127, 127, 126, 126, // 10784-10791
125, 126, 126, 126, 127, 127, 128, 128, // 10792-10799
128, 128, 128, 128, 127, 126, 126, 126, // 10800-10807
126, 126, 126, 127, 127, 128, 128, 128, // 10808-10815
128, 128, 128, 127, 127, 126, 126, 126, // 10816-10823
126, 126, 127, 127, 128, 128, 128, 128, // 10824-10831
128, 128, 127, 127, 126, 126, 126, 126, // 10832-10839
126, 127, 127, 127, 128, 128, 128, 128, // 10840-10847
128, 127, 127, 126, 126, 126, 126, 126, // 10848-10855
126, 127, 127, 128, 128, 128, 128, 128, // 10856-10863
128, 127, 127, 126, 126, 126, 126, 126, // 10864-10871
127, 127, 128, 128, 128, 128, 128, 128, // 10872-10879
127, 127, 126, 126, 126, 126, 126, 127, // 10880-10887
127, 128, 128, 128, 128, 128, 128, 127, // 10888-10895
127, 126, 126, 126, 126, 126, 126, 127, // 10896-10903
127, 128, 128, 128, 128, 128, 128, 127, // 10904-10911
126, 126, 126, 126, 126, 126, 127, 127, // 10912-10919
128, 128, 128, 128, 128, 128, 127, 127, // 10920-10927
126, 125, 126, 126, 126, 127, 127, 127, // 10928-10935
128, 128, 128, 128, 128, 127, 127, 126, // 10936-10943
125, 125, 126, 126, 127, 127, 127, 128, // 10944-10951
128, 128, 128, 128, 127, 127, 127, 126, // 10952-10959
125, 126, 126, 126, 127, 127, 128, 128, // 10960-10967
128, 128, 128, 128, 127, 127, 126, 126, // 10968-10975
126, 126, 126, 127, 127, 127, 128, 128, // 10976-10983
128, 128, 128, 127, 127, 126, 126, 126, // 10984-10991
126, 126, 127, 127, 127, 128, 128, 128, // 10992-10999
128, 128, 127, 127, 127, 126, 126, 126, // 11000-11007
126, 126, 127, 127, 128, 128, 128, 128, // 11008-11015
128, 127, 127, 127, 126, 125, 126, 126, // 11016-11023
126, 127, 127, 128, 128, 128, 128, 128, // 11024-11031
128, 127, 127, 126, 126, 126, 126, 126, // 11032-11039
127, 127, 127, 128, 128, 128, 128, 128, // 11040-11047
127, 127, 126, 126, 126, 126, 126, 127, // 11048-11055
127, 127, 128, 128, 128, 128, 128, 127, // 11056-11063
127, 127, 126, 126, 126, 126, 126, 127, // 11064-11071
127, 127, 128, 128, 128, 128, 127, 127, // 11072-11079
127, 126, 126, 126, 126, 126, 127, 127, // 11080-11087
127, 128, 128, 128, 128, 128, 127, 127, // 11088-11095
126, 126, 126, 126, 126, 127, 127, 127, // 11096-11103
128, 128, 128, 128, 128, 127, 127, 127, // 11104-11111
126, 126, 126, 126, 126, 127, 127, 128, // 11112-11119
128, 128, 128, 128, 128, 127, 127, 126, // 11120-11127
126, 126, 126, 126, 127, 127, 127, 128, // 11128-11135
128, 128, 128, 128, 127, 127, 126, 126, // 11136-11143
126, 126, 126, 127, 127, 127, 128, 128, // 11144-11151
128, 128, 128, 127, 127, 127, 126, 126, // 11152-11159
126, 126, 126, 127, 127, 128, 128, 128, // 11160-11167
128, 128, 127, 127, 127, 126, 126, 126, // 11168-11175
126, 126, 127, 127, 127, 128, 128, 128, // 11176-11183
128, 127, 127, 127, 126, 126, 126, 126, // 11184-11191
126, 127, 127, 127, 128, 128, 128, 128, // 11192-11199
128, 127, 127, 127, 126, 126, 126, 126, // 11200-11207
127, 127, 127, 128, 128, 128, 128, 128, // 11208-11215
127, 127, 127, 126, 126, 126, 126, 127, // 11216-11223
127, 127, 127, 128, 128, 128, 128, 127, // 11224-11231
127, 127, 126, 126, 126, 126, 126, 127, // 11232-11239
127, 127, 128, 128, 128, 128, 127, 127, // 11240-11247
127, 127, 126, 126, 126, 126, 127, 127, // 11248-11255
127, 128, 128, 128, 128, 128, 127, 127, // 11256-11263
127, 126, 126, 126, 126, 127, 127, 127, // 11264-11271
127, 128, 128, 128, 128, 127, 127, 127, // 11272-11279
126, 126, 126, 126, 127, 127, 127, 127, // 11280-11287
128, 128, 128, 128, 127, 127, 127, 126, // 11288-11295
126, 126, 126, 126, 127, 127, 127, 128, // 11296-11303
128, 128, 128, 127, 127, 127, 127, 126, // 11304-11311
126, 126, 126, 127, 127, 127, 128, 128, // 11312-11319
128, 128, 128, 127, 127, 127, 126, 126, // 11320-11327
126, 126, 127, 127, 127, 127, 128, 128, // 11328-11335
128, 128, 127, 127, 127, 126, 126, 126, // 11336-11343
126, 127, 127, 127, 127, 128, 128, 128, // 11344-11351
128, 127, 127, 127, 127, 126, 126, 126, // 11352-11359
127, 127, 127, 127, 128, 128, 128, 128, // 11360-11367
127, 127, 127, 127, 126, 126, 126, 126, // 11368-11375
127, 127, 127, 127, 128, 128, 128, 127, // 11376-11383
127, 127, 127, 126, 126, 126, 126, 127, // 11384-11391
127, 127, 127, 128, 128, 128, 128, 127, // 11392-11399
127, 127, 127, 126, 126, 126, 127, 127, // 11400-11407
127, 127, 128, 128, 128, 128, 127, 127, // 11408-11415
127, 127, 126, 126, 126, 127, 127, 127, // 11416-11423
127, 128, 128, 128, 128, 127, 127, 127, // 11424-11431
127, 126, 126, 126, 126, 127, 127, 127, // 11432-11439
127, 128, 128, 128, 127, 127, 127, 127, // 11440-11447
126, 126, 126, 126, 127, 127, 127, 127, // 11448-11455
128, 128, 128, 128, 127, 127, 127, 127, // 11456-11463
126, 126, 126, 127, 127, 127, 127, 127, // 11464-11471
128, 128, 128, 127, 127, 127, 127, 126, // 11472-11479
126, 126, 127, 127, 127, 127, 127, 128, // 11480-11487
128, 128, 127, 127, 127, 127, 126, 126, // 11488-11495
126, 126, 127, 127, 127, 127, 128, 128, // 11496-11503
128, 127, 127, 127, 127, 127, 126, 126, // 11504-11511
126, 127, 127, 127, 127, 128, 128, 128, // 11512-11519
128, 127, 127, 127, 127, 126, 126, 126, // 11520-11527
127, 127, 127, 127, 128, 128, 128, 128, // 11528-11535
127, 127, 127, 127, 126, 126, 126, 126, // 11536-11543
127, 127, 127, 127, 128, 128, 128, 128, // 11544-11551
127, 127, 127, 126, 126, 126, 126, 127, // 11552-11559
127, 127, 127, 128, 128, 128, 128, 127, // 11560-11567
127, 127, 127, 126, 126, 126, 127, 127, // 11568-11575
127, 127, 128, 128, 128, 128, 127, 127, // 11576-11583
127, 127, 126, 126, 126, 126, 127, 127, // 11584-11591
127, 127, 128, 128, 128, 128, 127, 127, // 11592-11599
127, 126, 126, 126, 126, 127, 127, 127, // 11600-11607
127, 128, 128, 128, 128, 127, 127, 127, // 11608-11615
126, 126, 126, 126, 127, 127, 127, 127, // 11616-11623
128, 128, 128, 128, 127, 127, 127, 127, // 11624-11631
126, 126, 126, 126, 127, 127, 127, 128, // 11632-11639
128, 128, 128, 128, 127, 127, 127, 126, // 11640-11647
126, 126, 126, 127, 127, 127, 127, 128, // 11648-11655
128, 128, 128, 127, 127, 127, 126, 126, // 11656-11663
126, 126, 127, 127, 127, 127, 128, 128, // 11664-11671
128, 128, 127, 127, 127, 126, 126, 126, // 11672-11679
126, 127, 127, 127, 127, 128, 128, 128, // 11680-11687
128, 127, 127, 127, 127, 126, 126, 126, // 11688-11695
126, 127, 127, 127, 128, 128, 128, 128, // 11696-11703
128, 127, 127, 127, 126, 126, 126, 126, // 11704-11711
127, 127, 127, 127, 128, 128, 128, 128, // 11712-11719
127, 127, 127, 127, 126, 126, 126, 127, // 11720-11727
127, 127, 127, 128, 128, 128, 128, 127, // 11728-11735
127, 127, 126, 126, 126, 126, 126, 127, // 11736-11743
127, 127, 128, 128, 128, 128, 127, 127, // 11744-11751
127, 127, 126, 126, 126, 126, 127, 127, // 11752-11759
127, 127, 128, 128, 128, 128, 127, 127, // 11760-11767
127, 126, 126, 126, 126, 127, 127, 127, // 11768-11775
127, 128, 128, 128, 128, 127, 127, 127, // 11776-11783
126, 126, 126, 126, 127, 127, 127, 127, // 11784-11791
128, 128, 128, 128, 127, 127, 127, 127, // 11792-11799
126, 126, 126, 126, 127, 127, 127, 128, // 11800-11807
128, 128, 128, 128, 127, 127, 127, 126, // 11808-11815
126, 126, 126, 127, 127, 127, 127, 128, // 11816-11823
128, 128, 128, 127, 127, 127, 126, 126, // 11824-11831
126, 126, 126, 127, 127, 127, 128, 128, // 11832-11839
128, 128, 127, 127, 127, 127, 126, 126, // 11840-11847
126, 126, 127, 127, 127, 128, 128, 128, // 11848-11855
128, 127, 127, 127, 127, 126, 126, 126, // 11856-11863
126, 127, 127, 127, 128, 128, 128, 128, // 11864-11871
128, 127, 127, 127, 126, 126, 126, 126, // 11872-11879
127, 127, 127, 127, 128, 128, 128, 128, // 11880-11887
127, 127, 127, 127, 126, 126, 126, 127, // 11888-11895
127, 127, 127, 128, 128, 128, 128, 127, // 11896-11903
127, 127, 127, 126, 126, 126, 127, 127, // 11904-11911
127, 127, 127, 128, 128, 128, 127, 127, // 11912-11919
127, 127, 126, 126, 126, 126, 127, 127, // 11920-11927
127, 127, 128, 128, 128, 128, 127, 127, // 11928-11935
127, 126, 126, 126, 126, 127, 127, 127, // 11936-11943
127, 128, 128, 128, 128, 127, 127, 127, // 11944-11951
127, 126, 126, 126, 127, 127, 127, 127, // 11952-11959
128, 128, 128, 128, 128, 127, 127, 127, // 11960-11967
126, 126, 126, 126, 127, 127, 127, 127, // 11968-11975
128, 128, 128, 128, 127, 127, 127, 127, // 11976-11983
126, 126, 126, 127, 127, 127, 127, 128, // 11984-11991
128, 128, 128, 127, 127, 127, 127, 126, // 11992-11999
126, 126, 126, 127, 127, 127, 127, 128, // 12000-12007
128, 128, 127, 127, 127, 127, 126, 126, // 12008-12015
126, 126, 127, 127, 127, 127, 128, 128, // 12016-12023
128, 128, 127, 127, 127, 127, 126, 126, // 12024-12031
126, 127, 127, 127, 127, 128, 128, 128, // 12032-12039
128, 127, 127, 127, 127, 126, 126, 126, // 12040-12047
127, 127, 127, 127, 127, 128, 128, 128, // 12048-12055
127, 127, 127, 127, 126, 126, 126, 127, // 12056-12063
127, 127, 127, 127, 128, 128, 128, 127, // 12064-12071
127, 127, 127, 126, 126, 126, 126, 127, // 12072-12079
127, 127, 127, 128, 128, 128, 128, 127, // 12080-12087
127, 127, 126, 126, 126, 126, 127, 127, // 12088-12095
127, 127, 128, 128, 128, 128, 127, 127, // 12096-12103
127, 127, 126, 126, 126, 126, 127, 127, // 12104-12111
127, 127, 128, 128, 128, 127, 127, 127, // 12112-12119
127, 126, 126, 126, 126, 127, 127, 127, // 12120-12127
127, 128, 128, 128, 128, 127, 127, 127, // 12128-12135
126, 126, 126, 126, 127, 127, 127, 127, // 12136-12143
128, 128, 128, 128, 127, 127, 127, 126, // 12144-12151
126, 126, 126, 127, 127, 127, 127, 128, // 12152-12159
128, 128, 128, 127, 127, 127, 127, 126, // 12160-12167
126, 126, 126, 127, 127, 127, 127, 128, // 12168-12175
128, 128, 127, 127, 127, 127, 126, 126, // 12176-12183
126, 126, 127, 127, 127, 127, 128, 128, // 12184-12191
128, 128, 127, 127, 127, 127, 126, 126, // 12192-12199
126, 127, 127, 127, 127, 128, 128, 128, // 12200-12207
128, 127, 127, 127, 127, 126, 126, 126, // 12208-12215
126, 127, 127, 127, 128, 128, 128, 128, // 12216-12223
127, 127, 127, 127, 126, 126, 126, 126, // 12224-12231
127, 127, 127, 127, 128, 128, 128, 128, // 12232-12239
127, 127, 127, 126, 126, 126, 126, 127, // 12240-12247
127, 127, 127, 128, 128, 128, 128, 127, // 12248-12255
127, 127, 127, 126, 126, 126, 127, 127, // 12256-12263
127, 127, 128, 128, 128, 128, 127, 127, // 12264-12271
127, 127, 126, 126, 126, 126, 127, 127, // 12272-12279
127, 127, 128, 128, 128, 127, 127, 127, // 12280-12287
127, 126, 126, 126, 126, 127, 127, 127, // 12288-12295
127, 128, 128, 128, 128, 127, 127, 127, // 12296-12303
127, 126, 126, 126, 127, 127, 127, 127, // 12304-12311
128, 128, 128, 128, 127, 127, 127, 127, // 12312-12319
126, 126, 126, 126, 127, 127, 127, 128, // 12320-12327
128, 128, 128, 127, 127, 127, 127, 126, // 12328-12335
126, 126, 126, 127, 127, 127, 127, 128, // 12336-12343
128, 128, 128, 128, 127, 127, 127, 126, // 12344-12351
126, 126, 126, 127, 127, 127, 127, 128, // 12352-12359
128, 128, 128, 127, 127, 127, 127, 126, // 12360-12367
126, 126, 126, 127, 127, 127, 128, 128, // 12368-12375
128, 128, 127, 127, 127, 127, 126, 126, // 12376-12383
126, 126, 127, 127, 127, 127, 128, 128, // 12384-12391
128, 128, 128, 127, 127, 127, 126, 126, // 12392-12399
126, 126, 126, 127, 127, 127, 128, 128, // 12400-12407
128, 128, 127, 127, 127, 126, 126, 126, // 12408-12415
126, 126, 127, 127, 127, 128, 128, 128, // 12416-12423
128, 128, 127, 127, 127, 126, 126, 126, // 12424-12431
126, 127, 127, 127, 128, 128, 128, 128, // 12432-12439
128, 127, 127, 127, 126, 126, 126, 126, // 12440-12447
126, 127, 127, 127, 128, 128, 128, 128, // 12448-12455
127, 127, 127, 126, 126, 126, 126, 126, // 12456-12463
127, 127, 127, 128, 128, 128, 128, 127, // 12464-12471
127, 127, 127, 126, 126, 126, 126, 127, // 12472-12479
127, 127, 128, 128, 128, 128, 127, 127, // 12480-12487
127, 127, 126, 126, 126, 126, 127, 127, // 12488-12495
127, 128, 128, 128, 128, 128, 127, 127, // 12496-12503
127, 126, 126, 126, 126, 126, 127, 127, // 12504-12511
127, 128, 128, 128, 128, 127, 127, 127, // 12512-12519
126, 126, 126, 126, 126, 127, 127, 127, // 12520-12527
128, 128, 128, 128, 127, 127, 127, 126, // 12528-12535
126, 126, 126, 126, 127, 127, 127, 128, // 12536-12543
128, 128, 128, 127, 127, 127, 127, 126, // 12544-12551
126, 126, 126, 127, 127, 127, 128, 128, // 12552-12559
128, 128, 128, 127, 127, 127, 126, 126, // 12560-12567
126, 126, 126, 127, 127, 127, 128, 128, // 12568-12575
128, 128, 127, 127, 127, 126, 126, 126, // 12576-12583
126, 126, 127, 127, 127, 128, 128, 128, // 12584-12591
128, 127, 127, 127, 127, 126, 126, 126, // 12592-12599
126, 127, 127, 127, 128, 128, 128, 128, // 12600-12607
128, 127, 127, 127, 126, 126, 126, 126, // 12608-12615
127, 127, 127, 127, 128, 128, 128, 128, // 12616-12623
127, 127, 127, 126, 126, 126, 126, 127, // 12624-12631
127, 127, 127, 128, 128, 128, 128, 127, // 12632-12639
127, 127, 126, 126, 126, 126, 126, 127, // 12640-12647
127, 127, 128, 128, 128, 128, 127, 127, // 12648-12655
127, 126, 126, 126, 126, 126, 127, 127, // 12656-12663
127, 128, 128, 128, 128, 128, 127, 127, // 12664-12671
127, 126, 126, 126, 126, 126, 127, 127, // 12672-12679
127, 128, 128, 128, 128, 127, 127, 127, // 12680-12687
126, 126, 126, 126, 126, 127, 127, 127, // 12688-12695
128, 128, 128, 128, 127, 127, 127, 126, // 12696-12703
126, 126, 126, 126, 127, 127, 127, 128, // 12704-12711
128, 128, 128, 128, 127, 127, 127, 126, // 12712-12719
126, 126, 126, 127, 127, 127, 127, 128, // 12720-12727
128, 128, 128, 127, 127, 127, 126, 126, // 12728-12735
126, 126, 126, 127, 127, 127, 128, 128, // 12736-12743
128, 128, 128, 127, 127, 126, 126, 126, // 12744-12751
126, 126, 127, 127, 127, 128, 128, 128, // 12752-12759
128, 128, 127, 127, 127, 126, 126, 126, // 12760-12767
126, 126, 127, 127, 128, 128, 128, 128, // 12768-12775
128, 127, 127, 127, 126, 126, 126, 126, // 12776-12783
126, 127, 127, 128, 128, 128, 128, 128, // 12784-12791
127, 127, 127, 126, 126, 126, 126, 126, // 12792-12799
127, 127, 127, 128, 128, 128, 128, 128, // 12800-12807
127, 127, 126, 126, 126, 126, 126, 127, // 12808-12815
127, 127, 128, 128, 128, 128, 128, 127, // 12816-12823
127, 127, 126, 126, 126, 126, 126, 127, // 12824-12831
127, 128, 128, 128, 128, 128, 127, 127, // 12832-12839
127, 126, 126, 126, 126, 126, 127, 127, // 12840-12847
127, 128, 128, 128, 128, 128, 127, 127, // 12848-12855
126, 126, 126, 126, 126, 127, 127, 127, // 12856-12863
128, 128, 128, 128, 128, 127, 127, 127, // 12864-12871
126, 126, 126, 126, 126, 127, 127, 128, // 12872-12879
128, 128, 128, 128, 127, 127, 127, 126, // 12880-12887
126, 126, 126, 126, 127, 127, 128, 128, // 12888-12895
128, 128, 128, 127, 127, 127, 126, 126, // 12896-12903
126, 126, 126, 127, 127, 127, 128, 128, // 12904-12911
128, 128, 128, 127, 127, 127, 126, 126, // 12912-12919
126, 126, 127, 127, 127, 128, 128, 128, // 12920-12927
128, 128, 127, 127, 126, 126, 126, 126, // 12928-12935
126, 126, 127, 127, 127, 128, 128, 128, // 12936-12943
128, 127, 127, 127, 126, 126, 126, 126, // 12944-12951
126, 127, 127, 127, 128, 128, 128, 128, // 12952-12959
128, 127, 127, 126, 126, 126, 126, 126, // 12960-12967
127, 127, 127, 128, 128, 128, 128, 128, // 12968-12975
127, 127, 127, 126, 126, 126, 126, 127, // 12976-12983
127, 127, 127, 128, 128, 128, 128, 127, // 12984-12991
127, 127, 126, 126, 126, 126, 127, 127, // 12992-12999
127, 127, 128, 128, 128, 128, 127, 127, // 13000-13007
127, 126, 126, 126, 126, 126, 127, 127, // 13008-13015
127, 128, 128, 128, 128, 127, 127, 127, // 13016-13023
126, 126, 126, 126, 126, 127, 127, 127, // 13024-13031
128, 128, 128, 128, 127, 127, 127, 127, // 13032-13039
126, 126, 126, 126, 127, 127, 127, 128, // 13040-13047
128, 128, 128, 127, 127, 127, 127, 126, // 13048-13055
126, 126, 126, 127, 127, 127, 128, 128, // 13056-13063
128, 128, 128, 127, 127, 127, 126, 126, // 13064-13071
126, 126, 127, 127, 127, 127, 128, 128, // 13072-13079
128, 128, 127, 127, 127, 126, 126, 126, // 13080-13087
126, 126, 127, 127, 127, 128, 128, 128, // 13088-13095
128, 127, 127, 127, 127, 126, 126, 126, // 13096-13103
126, 127, 127, 127, 128, 128, 128, 128, // 13104-13111
127, 127, 127, 127, 126, 126, 126, 126, // 13112-13119
127, 127, 127, 128, 128, 128, 128, 128, // 13120-13127
127, 127, 127, 127, 126, 126, 126, 127, // 13128-13135
127, 127, 127, 128, 128, 128, 128, 127, // 13136-13143
127, 127, 126, 126, 126, 126, 127, 127, // 13144-13151
127, 127, 128, 128, 128, 128, 127, 127, // 13152-13159
127, 126, 126, 126, 126, 126, 127, 127, // 13160-13167
127, 128, 128, 128, 128, 127, 127, 127, // 13168-13175
127, 126, 126, 126, 126, 127, 127, 127, // 13176-13183
127, 128, 128, 128, 127, 127, 127, 127, // 13184-13191
126, 126, 126, 126, 127, 127, 127, 127, // 13192-13199
128, 128, 128, 128, 127, 127, 127, 127, // 13200-13207
126, 126, 126, 127, 127, 127, 127, 128, // 13208-13215
128, 128, 128, 127, 127, 127, 127, 126, // 13216-13223
126, 126, 127, 127, 127, 127, 127, 128, // 13224-13231
128, 128, 127, 127, 127, 127, 126, 126, // 13232-13239
126, 126, 127, 127, 127, 127, 128, 128, // 13240-13247
128, 127, 127, 127, 127, 127, 126, 126, // 13248-13255
126, 127, 127, 127, 127, 128, 128, 128, // 13256-13263
128, 127, 127, 127, 127, 126, 126, 126, // 13264-13271
127, 127, 127, 127, 127, 128, 128, 128, // 13272-13279
127, 127, 127, 127, 127, 126, 126, 127, // 13280-13287
127, 127, 127, 127, 128, 128, 128, 127, // 13288-13295
127, 127, 127, 126, 126, 126, 126, 127, // 13296-13303
127, 127, 127, 128, 128, 128, 128, 127, // 13304-13311
127, 127, 127, 126, 126, 126, 127, 127, // 13312-13319
127, 127, 127, 128, 128, 128, 127, 127, // 13320-13327
127, 127, 126, 126, 126, 127, 127, 127, // 13328-13335
127, 127, 128, 128, 128, 127, 127, 127, // 13336-13343
127, 126, 126, 126, 126, 127, 127, 127, // 13344-13351
127, 128, 128, 128, 128, 127, 127, 127, // 13352-13359
127, 126, 126, 126, 127, 127, 127, 127, // 13360-13367
128, 128, 128, 128, 127, 127, 127, 127, // 13368-13375
126, 126, 126, 127, 127, 127, 127, 127, // 13376-13383
128, 128, 128, 127, 127, 127, 127, 126, // 13384-13391
126, 126, 126, 127, 127, 127, 127, 128, // 13392-13399
128, 128, 127, 127, 127, 127, 126, 126, // 13400-13407
126, 126, 127, 127, 127, 127, 128, 128, // 13408-13415
128, 127, 127, 127, 127, 127, 126, 126, // 13416-13423
126, 127, 127, 127, 127, 128, 128, 128, // 13424-13431
127, 127, 127, 127, 127, 126, 126, 126, // 13432-13439
127, 127, 127, 127, 127, 128, 128, 128, // 13440-13447
127, 127, 127, 127, 126, 126, 126, 126, // 13448-13455
127, 127, 127, 127, 127, 128, 128, 127, // 13456-13463
127, 127, 127, 126, 126, 126, 126, 127, // 13464-13471
127, 127, 127, 127, 128, 128, 127, 127, // 13472-13479
127, 127, 127, 126, 126, 126, 127, 127, // 13480-13487
127, 127, 127, 128, 128, 128, 127, 127, // 13488-13495
127, 127, 126, 126, 126, 127, 127, 127, // 13496-13503
127, 127, 128, 128, 128, 127, 127, 127, // 13504-13511
127, 126, 126, 126, 126, 127, 127, 127, // 13512-13519
127, 128, 128, 128, 127, 127, 127, 127, // 13520-13527
127, 126, 126, 126, 127, 127, 127, 127, // 13528-13535
128, 128, 128, 128, 127, 127, 127, 127, // 13536-13543
126, 126, 126, 127, 127, 127, 127, 128, // 13544-13551
128, 128, 128, 127, 127, 127, 127, 126, // 13552-13559
126, 126, 126, 127, 127, 127, 128, 128, // 13560-13567
128, 128, 127, 127, 127, 127, 126, 126, // 13568-13575
126, 126, 127, 127, 127, 127, 128, 128, // 13576-13583
128, 127, 127, 127, 127, 127, 126, 126, // 13584-13591
126, 127, 127, 127, 127, 128, 128, 128, // 13592-13599
128, 127, 127, 127, 126, 126, 126, 126, // 13600-13607
127, 127, 127, 127, 128, 128, 128, 128, // 13608-13615
127, 127, 127, 127, 126, 126, 126, 126, // 13616-13623
127, 127, 127, 127, 128, 128, 128, 128, // 13624-13631
127, 127, 127, 126, 126, 126, 126, 127, // 13632-13639
127, 127, 127, 128, 128, 128, 128, 127, // 13640-13647
127, 127, 126, 126, 126, 126, 127, 127, // 13648-13655
127, 127, 128, 128, 128, 128, 127, 127, // 13656-13663
127, 126, 126, 126, 126, 127, 127, 127, // 13664-13671
127, 128, 128, 128, 128, 127, 127, 127, // 13672-13679
127, 126, 126, 126, 126, 127, 127, 127, // 13680-13687
127, 128, 128, 128, 128, 127, 127, 127, // 13688-13695
126, 126, 126, 126, 127, 127, 127, 128, // 13696-13703
128, 128, 128, 128, 127, 127, 127, 127, // 13704-13711
126, 126, 126, 127, 127, 127, 127, 128, // 13712-13719
128, 128, 128, 127, 127, 127, 127, 126, // 13720-13727
126, 126, 126, 127, 127, 127, 128, 128, // 13728-13735
128, 128, 127, 127, 127, 127, 126, 126, // 13736-13743
126, 126, 127, 127, 127, 128, 128, 128, // 13744-13751
128, 127, 127, 127, 127, 127, 126, 126, // 13752-13759
126, 127, 127, 127, 127, 128, 128, 128, // 13760-13767
128, 127, 127, 127, 127, 126, 126, 126, // 13768-13775
127, 127, 127, 127, 128, 128, 128, 128, // 13776-13783
127, 127, 127, 127, 126, 126, 126, 127, // 13784-13791
127, 127, 127, 127, 128, 128, 128, 128, // 13792-13799
127, 127, 127, 127, 126, 126, 127, 127, // 13800-13807
127, 127, 127, 128, 128, 128, 128, 127, // 13808-13815
127, 127, 127, 126, 126, 126, 127, 127, // 13816-13823
127, 127, 127, 128, 128, 128, 127, 127, // 13824-13831
127, 127, 126, 126, 126, 127, 127, 127, // 13832-13839
127, 127, 128, 128, 128, 127, 127, 127, // 13840-13847
127, 126, 126, 126, 127, 127, 127, 127, // 13848-13855
127, 128, 128, 128, 127, 127, 127, 127, // 13856-13863
127, 126, 126, 127, 127, 127, 127, 127, // 13864-13871
127, 128, 128, 127, 127, 127, 127, 127, // 13872-13879
126, 126, 126, 127, 127, 127, 127, 127, // 13880-13887
128, 128, 127, 127, 127, 127, 127, 126, // 13888-13895
126, 126, 127, 127, 127, 127, 127, 128, // 13896-13903
128, 127, 127, 127, 127, 127, 126, 126, // 13904-13911
126, 127, 127, 127, 127, 128, 128, 128, // 13912-13919
128, 127, 127, 127, 127, 127, 126, 126, // 13920-13927
127, 127, 127};// 13928-13930


#endif	/* SAMPLE_H */
    </code>
</pre>

## Ensamblado

El ensamblado de esta caja es bastante laborioso. He creado una animación del montaje de las piezas fundamentales de la caja para que se pueda apreciar mejor el orden a seguir. Lo vemos en el siguiente video.

<video class="center" controls autoplay preload>
  <source src="/assets/2020-08-10-construyendo-una-caja-de-musica/Assembly.mp4" type="video/mp4">
</video>

El primer paso es soldar todos los componentes de la placa base. Esta placa la he encargado a china dado que las especificaciones de diseño eran demasiado precisas como para hacerla con técnicas caseras. El espacio mínimo entre pistas y el tamaño de las pistas es de tan sólo 6 milésimas de pulgada. En las siguientes imágenes se observan los dos lados de la placa base con los componentes ya soldados. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/MontajeEstatorYPlaca.jpg" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/MontajeEstatorYPlaca.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/MontajeEstatorYPlacaInferior.jpg" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/MontajeEstatorYPlacaInferior.jpg"
alt="Schematic" 
class="center" />
</a>

Las placas para alojar los diodos LED sí tienen especificaciones más accesibles para las técnicas caseras que explico <a href="/electronica/2020/07/13/pcb-con-cnc-1610.html">en este otro artículo</a>. Son un total de ocho placas con cuatro LEDs cada una que van soldadas a sus correspondientes puertos en la placa base. Los cables de cada placa deben quedar alojados dentro del hueco del estátor junto con el motor N20. Por ese motivo he empleado hilo de cobre esmaltado de 300 micras que ocupa muy poco espacio y posee suficiente grosor para la corriente que demandan los diodos. A continuación muestro algunas imágenes con el proceso de soldado de las placas de iluminación.  

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLedCnc.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbLedCnc.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLedMontaje.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbLedMontaje.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbLedSoldadura.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbLedSoldadura.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbSoldadura01.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbSoldadura01.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbSoldadura02.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbSoldadura02.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/PcbSoldadura03.jpg">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/PcbSoldadura03.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

Una vez soldadas las placas de iluminación el trabajo de electrónica está practicamente terminado. Podemos plantear la placa base en el armazón de la caja de música y lijar las partes que requieran de algún ajuste como los cajones. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ChasisEstator.jpg" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ChasisEstator.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ApantalladoLateral.jpg" >
<img 
  align="left" 
  src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ApantalladoLateral.jpg" 
  alt="Main" 
  width="280"
/>
</a>

Para conseguir el efecto estroboscópico es necesario que lo único que vean nuestros ojos de la escena sea la luz emitida por las placas de iluminación. Si la animación recibe luz continua del exterior, si bien se puede apreciar levemente el efecto estroboscópico, la secuencia queda altamente borrosa. Para evitar eso utilizamos cristales tintados que impedirán el paso de la luz exterior y permitirán ver el interior de la caja cuando las luces de las placas de iluminación se enciendan. 

Para esta caja de música utilizaremos láminas de polipropileno transparente de 400 micras de grosor a las que adheriremos láminas utilizadas para tintar cristales en vehículos. El polipropileno es bastante maleable y nos permitirá cortar con facilidad y ajustar los paneles a los laterales de la caja de música. Utilizaremos pegamento de cianoacrilato para fijar el policarbonato a las columnas laterales y la tapa de la caja. A continuación vemos algunas imágenes del armazón de la caja con los paneles laterales ya montados. 

<table>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ChasisApantalladoLateral01.png">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ChasisApantalladoLateral01.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ChasisApantalladoLateral02.png">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ChasisApantalladoLateral02.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

Repetiremos el mismo proceso de corte de las láminas de policarbonato y adhesión de las láminas tintadas con las ventanas de la tapa superior de la caja. Estas ventanas permitirán ver la animación también desde el ángulo superior aumentando la percepción de tridimensionalidad de la escena. 

<table>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ApantalladoCubierta01.png">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ApantalladoCubierta01.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/ApantalladoCubierta02.png">
            <img 
            src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/ApantalladoCubierta02.jpg"
            alt="Schematic" 
            class="center-100" />
            </a>
        </td>
    </tr>
</table>

Como detalle añadiremos una lámina más de polipropileno alrededor del rotor. Esta lámina la lijaremos en lugar de tintarla para que difumine las luces LED de la columna de iluminación. Además añadiremos imanes de neodimio cilíndricos de 5mm en el hueco de cada cajón. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/CajonesImanes.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/CajonesImanes.jpg"
alt="Schematic" 
class="center" />
</a>

Situamos el interruptor (cables rojo y negro) y el altavoz (cables morado y marrón) en sus alojamientos correspondientes en la base de la caja. Al encajar la placa base en los dos soportes centrales podremos atornillarla con tornillos de 3mm x 30mm de longitud. 

Una vez atornillada la placa base podemos utilizar el hueco de la batería para acceder al ICSP y programar el PIC18F2550 con el firmware que analizamos en la sección anterior. Veamos algunas imágenes de este proceso a continuación. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/EnsambladoPcbChasis.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/EnsambladoPcbChasis.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/InferiorPickit.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/InferiorPickit.jpg"
alt="Schematic" 
class="center" />
</a>

El rotor está impreso en una resina de color blanquecino y en dos mitades debido a la limitación del volúmen de impresión de la <i>Anycubic Photon</i>. Cada una de las mitades se adhiere con tornillos de 2mm a una pieza cilíndrica que encaja con el eje del motor N20. Además incluiremos imanes de neodimio cilíndricos de 2mm de diámetro y 5mm de longitud en la cara interna de cada columna del rotor. A continuación vemos imágenes del rotor listo para ser incorporado sobre el estátor. 


<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Rotor01.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Rotor01.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Rotor02.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Rotor02.jpg"
alt="Schematic" 
class="center" />
</a>

Tras encajar el rotor en el eje del motor éste debería girar sin problema. Una vez realizado este paso la caja de música estaría completa. A continuación dejo algunas imágenes del ensamblado final y los resultados. 

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final01.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final01.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final02.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final02.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final03.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final03.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final04.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final04.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final05.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final05.jpg"
alt="Schematic" 
class="center" />
</a>

<a href="/assets/2020-08-10-construyendo-una-caja-de-musica/Final06.png" >
<img 
src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/Final06.jpg"
alt="Schematic" 
class="center" />
</a>

## Descargas

A continuación se encuentra la lista de ficheros STL necesarios para la construcción de esta caja de música. Todas las piezas pueden ser impresas en horizontal en una <i>Anycubic Photon</i> salvo la base y la tapa de la caja de música. Estas deben ser impresas en vertical. 

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadBase.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadBase.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_Base.stl">BEZ_Base.stl</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadTop.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadTop.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_Top.stl">BEZ_Top.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadBatteryCover.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadBatteryCover.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_BatteryCover.stl">BEZ_BatteryCover.stl</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadDrawer.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadDrawer.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_Drawer.stl">BEZ_Drawer.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadStator.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadStator.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_Stator.stl">BEZ_Stator.stl</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadRotorAssemblyPart.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadRotorAssemblyPart.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_RotorAssemblyPart.stl">BEZ_RotorAssemblyPart.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadRotor.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadRotor.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_RotorHalf1.stl">BEZ_RotorHalf1.stl</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadRotor.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadRotor.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_RotorHalf2.stl">BEZ_RotorHalf2.stl</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadRotorHalfEmpty.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadRotorHalfEmpty.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/BEZ_RotorHalfEmpty.stl">BEZ_RotorHalfEmpty.stl</a>
        </td>
    </tr>
</table>

Dejo aquí también los ficheros Gerber correspondientes a las placas.

<table class="center">
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberTopCopper.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberTopCopper.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Top Copper.GBR">BEZ_Main_V04 - CADCAM Top Copper.GBR</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberBottomCopper.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberBottomCopper.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Bottom Copper.GBR">BEZ_Main_V04 - CADCAM Bottom Copper.GBR</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberTopSilk.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberTopSilk.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Top Silk Screen.GBR">BEZ_Main_V04 - CADCAM Top Silk Screen.GBR</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberBottomSilk.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberBottomSilk.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Bottom Silk Screen.GBR">BEZ_Main_V04 - CADCAM Bottom Silk Screen.GBR</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberTopResist.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberTopResist.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Top Solder Resist.GBR">BEZ_Main_V04 - CADCAM Top Solder Resist.GBR</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberBottomResist.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberBottomResist.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Bottom Solder Resist.GBR">BEZ_Main_V04 - CADCAM Bottom Solder Resist.GBR</a>
        </td>
    </tr>
    <tr>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberDrill.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberDrill.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Drill.DRL">BEZ_Main_V04 - CADCAM Drill.DRL</a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/DownloadGerberMechanical.png">
                <img 
                src="/assets/2020-08-10-construyendo-una-caja-de-musica/low/DownloadGerberMechanical.jpg" 
                width="200" />
            </a>
        </td>
        <td>
            <a href="/assets/2020-08-10-construyendo-una-caja-de-musica/downloads/gerber/BEZ_Main_V04 - CADCAM Mechanical 1.GBR">BEZ_Main_V04 - CADCAM Mechanical 1.GBR</a>
        </td>
    </tr>
</table>