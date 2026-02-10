---
layout: default
title: Fairhillbillies SU Piston Position Sensor
tip: Fairhillbillies SU piston position sensor
date:   2025-11-15 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position, measurement ] # applies to book level
  themes: [ SU Piston Position ] # applies to chapter level
---
{% include mermaid.html %}
{% include mathjax.html %}

Last update {{ page.date | date: "%d %b %Y" }}.

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/3p.7.2/
{% endcapture %}

# Fairhillbillies SU Piston Position Sensor

> The modern mechanical carburettor is a highly developed
> device capable of accurately delivering the incorrect air/fuel mixture.

## Principle of Operation

Sensing the piston position is facilitated with three components:

* A **target pattern** of stripes residing in the piston groove.
The position of the target directly relates to that of the needle.

* An **optical transducer** residing at the guide key position in the 
carburettor body.
The transducer detects
the alignment of a stripe with one of three positions.

* A **decoder circuit** residing at a convenient location within the vehicle.

The **target** rises and falls along with the piston. The **transducer** 
senses the instantaneous pattern alignment. The **decoder** converts the
pattern alignment evolution into a position number.  Ultimately the
decoder output is displayed and transmitted via CAN-bus for further
processing.

## TL;DR Prototype Preview:

The following sections describe the prototype stages of development
of the piston position sensor. 

Here's a drawing of the installed target and sensor:

{% include figure.html
           img-dir=image-dir
           img-file='assy.full.4.png'
           alt='Drawing of target and sensor'
           caption='Target and Sensor assembled into HIF44'
%}

Here's a close up of the 3-cell transducer mounted in the location of the
standard guide key. Only one cell aligns with a stripe at a time.
The alternative guide key is also depicted.

{% include figure.html
           img-dir=image-dir
           img-file='newkey.sensor.png'
           alt='Drawing of new key and sensor'
           caption='Transducer and new Guide Key'
%}

## Target Pattern

The target is a black FR4 printed circuit board.
The pattern is white silkscreen.
In the figure below the pattern is shown negative: the white silkscreen stripes
are shown in green and the black FR4 gaps are the spaces between the stripes.

Each stripe in the pattern is 1/24" wide and each gap
is 2/24" wide. The pattern repetition is thus 3/24" = 1/8".
By convention, the needle stages are also set at 1/8" increments
hence the target pattern repeats once per needle stage.
As will be described, position detection uniquely resolves each of the three
stripe positions within the pattern repetition as a 'tooth'.  Thus the system
reports 3 tooth positions per needle stage.

At the far left end of the target is a double wide stripe which acts as
a position reference indicator when the piston is at its lowest position
resting on the bridge of the carburettor throat.

{% include figure.html
           img-dir=image-dir
           img-file='3p_target_7.2.png'
           alt='Drawing of 3p_target_7.2 pcb'
           caption='3p_target_7.2 target pattern pcb'
%}

## Optical Transducer/Sensor

The transducer is mounted on a flexible printed circuit board,
the assembly of which is collectively referred to as the *sensor*.
The transducer is comprised of three cells, each comprised of an infrared
light emitting diode and phototransistor pair.
The footprint of the
transducer area is the red structure at the upper left in the following drawing.
Most of the sensor is taken up by the red and blue wiring that is used to
route signals from the transducer to the external connections, bottom right.

{% include figure.html
           img-dir=image-dir
           img-file='3p_sensor_7.2.png'
           alt='Drawing of 3p_sensor_7.2 flex pcb'
           caption='3p_sensor_7.2 transducer flex pcb'
%}

The sensor follows a tortuous path to lead from the transducer to the
external connections:

{% include figure.html
           img-dir=image-dir
           img-file='sensor.conformal.1.png'
           alt='Drawing of conformal sensor'
           caption='Sensor in conformal attitude'
%}

## Decoder Circuit

The decoder circuit activates and monitors the sensor to identify the 
tooth value of the target.  The tooth value is presented as a 0-31 number
on the CAN bus and as a 0-5Volt analog output.  The block diagram
and description of the decoder is presented below.

<pre class="mermaid">
    graph LR
      Sensor -. Ee .-> Target
      Target -. &Gamma;Ee .-> Sensor
      Drive --Ie--> Sensor
      Mute --b y r--> Drive
      Sensor --Iq--> TIA
      TIA --Vt--> Comparator
      Reference --Vr--> Comparator
      Reference --Vr, Vb--> TIA
      Reference --Vd--> Drive
      Comparator --P B Y R--> Counter
      Counter --Vtooth--> Analog
      Counter --Ntooth--> CAN
</pre>
<p style="text-align: center;" class="textFig">Decoder Block Diagram </p>

### __Reference circuit__

  The reference circuit provides the set of reference voltages
  that are shared between other blocks in the circuit.

  * $V_r$ is the primary 5.0 Volt reference derived from a precision regulator.

  * $V_d$ is the reference for driving transducer LED brightness.
  It is nominally set to 2.5 Volts and buffered by the operational amplifier.

  * $V_b$ is the reference for transducer phototransistor balance current.
  It is developed by the buffered instrumentation amplifier as
  $V_b = V_d + V_r$ .

  {% include ghost.html
           img-dir=image-dir
           img-file='blockReferencePath.svg'
       alt='reference voltages'
       caption='Reference voltages shared across blocks'
  %}

  
### __Target circuit__

  The Target circuit is optical and provides a variable reflection of
  incoming infrared irradiance, $E_e$. 
  The brightness of reflected light varies
  as its stripes pass the transducer due to piston movement.
  The reflection coefficient, &Gamma;, is a scalar that varies from 1
  for perfect reflection to 0 for no reflection. &Gamma; characterizes
  the ratio of reflected to incoming light.

  {% include ghost.html
           img-dir=image-dir
           img-file='blockTarget1.svg'
       alt='target reflecting light'
       caption='Incoming irradiance reflecting from target with &Gamma; loss'
  %}


### __Transducer__

  The transducer consists of three cells, each with an LED
  (Light Emitting Diode) and a phototransistor.  In the drawing
  below the LEDs are shown as the clear devices below the black 
  phototransistors.

  {% include ghost.html
           img-dir=image-dir
           img-file='transducerOnPCB.1.png'
       alt='transducer cells'
       caption='Transducer cells $Blu$, $Yel$ and $Red$ (left to right)'
  %} 

  For convenience, each of the cells is designated as either
  *Blu*, *Yel*, or *Red*
  to identify its position in the transducer.  The width of the devices
  making up a cell is somewhat less than the width of a target stripe.
  The cells are spaced apart by one stripe width[^pitch].  This configuration
  retains the feature that only one cell aligns with a stripe at a time.

[^pitch]: The wide spacing of the transducer cells was motivated by two factors.

    * Cell to cell crosstalk occurs when one cell aligns with a stripe
    and brightly illuminates it.  Then its neighbor cell also sees an increase
    in brightness.  Early transducer designs, without this spacing, were
    unworkable due to this effect.  The added extra space does significantly
    reduce this crosstalk, however the dynamic range of the transducer is
    still quite limited.  This led to the need for the muting circuit.

    * Wire routing to the cells in the sensor is simplified. Tight
    cell-to-cell spacing forces vias to be placed within the solder
    lands of the devices.  This is a bad practice making assembly difficult
    and leading to unreliable solder joints.  The wider spacing
    relieves this problem.

    The wide cell spacing has the downside of limiting the available
    space for the piston key's tongue.  A shorter tongue may allow
    for an increase of piston runout.


### __Sensor circuit__

  Each cell LED of the sensor transducer irradiates the target, $E_e$,
  which reflects $\Gamma E_e$ onto the companion phototransistor,
  changing its current, $I_q$.  Here is depicted the Red cell with
  LED $D_R$ and phototransistor $Q_R$.  The current driving the LED
  is $I_e$ and the responding current in the phototransistor is $I_q$.

  {% include ghost.html
           img-dir=image-dir
           img-file='blockTransducer1.svg'
       alt='transducer cell interacting with target'
       caption='Transducer cell interacting with Target'
  %} 

  The drawing above is a bit misleading as the transducer cell is actually
  about the same width as a target stripe.  The cell is also oriented
  $90^\circ$ from that shown.

  There is considerable variation in the characteristics of each of these
  components.  The proportionality of the LED $E_e$ irradiance to its
  $I_e$ current
  is linear, but differs from device to device.  Similarly the $I_q$
  to $E_q$ ratio of the individual phototransistors is so variable that
  manufacturers commonly provide these devices binned to ranges.  The
  target is subject to lithography and mechanical variability.

  As a result of the sensor variability, the supporting circuitry provides
  a means to *tune* each cell in the transducer individually for
  uniform operation.


### __Drive circuit__
  
  Each LED in the transducer requires a unique current, $I_e$,
  that sets its reference irradiance, $E_e$. All cells derive their
  individual $I_e = V_e / R_e$ from the common $V_d$ reference voltage.

{% include ghost.html
           img-dir=image-dir
           img-file='blockDrivePath.svg'
           alt='schematic of LED Driver circuit'
           caption='Transducer $D_Y$ LED current driver'
%}

The $V_d$ reference drive voltage is tuned to the cell-specific $V_e$ by the
cell's $R_d$ potentiometer. That is, if $0 \le \kappa \le 1$ represents
the position of the potentiometer then

$$
V_e = \kappa V_d \label{eq:ledKappa} \tag{1}.
$$

The buffered instrumentation amplifier, $IA$, forces the same
$V_e$ potential to appear across resistor $R_e$ and determines $I_e$.
The $E_e$ irradiance is proportinal to $I_e$ which is the $D_{Y}$ LED
current shown here.  Introducing $\alpha$, the device-specific current to
irradiance scaling constant, yields

$$
E_e = {\alpha \kappa V_d \over R_e} \label{eq:ledEe} \tag{2}.
$$

All of the transducer LEDs derive their drive current in proportion to
the same drive voltage $V_d$ even though each LED has a unique $I_e$.
This means that once each $R_d$ potentiometer has been set to produce a
tuned level of $E_e$, subsequently all LED's brightness can be varied
simultaneously by changing only $V_d$ while retaining the same
*relative* brightness.

It is also useful to note that measuring the voltage $V_e$ across $R_e$
provides a way to monitor the LED current.
For convenience, selecting $R_e = 1000 {\Omega}$
yields $V_e$ directly as milliAmps.

### __Mute circuit__

Due to optical crosstalk[^pitch] it is necessary to illuminate only one
transducer LED at a time.  This provides for good discrimination in the
comparator stage.

{% include ghost.html
           img-dir=image-dir
           img-file='blockMutePath.svg'
           alt='schematic of Mute circuit'
           caption='Mute operation showing $D_Y$ and $D_B$ LEDs muted'
%}

Muting of a transducer LED ($D_R$, $D_Y$, $D_B$) is achieved by
shunting its $I_e$ drive current to ground
via the $Q_m$ transistor.  Each $Q_m$ transistor is driven through the $R_m$
resistor to be either saturated or off by virtue of the $V_m$ TTL level voltage
provided by the *Mute Cycler*.  Diode $D_m$ provides a bit of
offset to the $V_{ce} sat$ voltage of $Q_m$ so that the drive current source 
providing $I_e$ does not need to greatly shift its output voltage
as it maintains the constant $I_e$.  This allows for the *Mute Cycler* to
run at a relatively high rate[^muterate].

[^muterate]: The rate of the mute circuit is limited primarily by the settling time of the phototransistor.  The TIA circuit, which allows the phototransistor to drive a virtual ground, minimizes this settling time to 25 &micro;sec.  In practice the mute circuit provides 50 &micro;sec for the settling.

<pre class="mermaid" style="text-align: center;">
    graph LR
      Blu --> Yel
      Yel --> Red
      Red --> Blu
</pre>
<p style="text-align: center;" class="textFig">Mute Cycler State Diagram</p>

The mute cycler is realized with a common microprocessor running with
a 16Mhz clock.  The cycler outputs are 5V TTL levels.
The mute cycler allows each of the transducer LEDs to illuminate, in turn,
for a 50 &micro;sec period. When a target stripe is aligned with one of
the transducer cells, a pulse train is produced with a
$3 * 50 = 150 \mu sec$ period.

In the [section for tuning](#tuning) there is described a special mode of
operation of the mute circuit that modifies the _Mute Cycler_
behavior and allows each of the three _Blu_, _Yel_ and _Red_
states to be entered statically by pressing the _tune_ button.
To enter this mode the _tune_ button must be held during power up
of the [Decoder Circuit](#decoder-circuit).  The mute circuit provides
a set of indicator LEDs ($D_i^R$, $D_i^Y$, $D_i^B$) that provide visual
confirmation of the corresponding illuminated transducer LED.

### __TransImpedance Amplifier circuit__

The phototransistor requires special attention to ensure adequate performance:
Its $V_{ce}$ voltage should be maintained at 5 volts.  Its $I_q$ collector
current should be set to a nominal 1 mA value.  The collector load
impedance should be 0 &Omega; for fast response. Tuning for the
individual device $\beta$; is required.  And finally the environmental drift,
due to temperature, humidity, etc., should be matched to the companion LED.
The TIA circuit accounts for all of those requirements.

{% include ghost.html
           img-dir=image-dir
           img-file='blockTiaPath.svg'
           alt='schematic of TIA circuit'
           caption='TIA termination of $Q_B$ phototransistor'
%}

A TransImpedance Amplifier provides termination for each
phototransistor in the sensor transducer.

The $V_r = 5 V$ reference voltage is applied to the $OA^+$ input. 
The $V_t$ output voltage of the operational amplifier swings to hold
the $OA^-$ input at the same $V_r$ voltage through the $R_t$ feedback
resistor.  As a result the feedback current is $I_f = (V_t - V_r) / R_t$.
This establishes the desired $V_{ce} = 5 V$ and 0 &Omega;
short-circuit load conditions. 

Meanwhile the voltage across the $R_b$ balance resistor is 
$V_b - V_r = V_d$.  That is the $R_b$ voltage drop is the same $V_d$ drive 
voltage used to bias the LEDs.  The balance current in $R_b$ is thus 
$I_b = V_d / R_b$ and is used to set the nominal value of $I_q$.

The $I_q = I_b + I_f$ phototransistor current is the sum of balance and
feedback currents.  Introducing the photo-current to electron-current
conversion constant, $\gamma$, and the device-specific current gain,
$\beta$, then $\gamma \Gamma E_e$ is the base current
and the collector current is $I_q = \beta \gamma \Gamma E_e$.
Rearranging yields $I_f = \beta \gamma \Gamma E_e - I_b$ so that

$$
V_t = V_r + R_t( \beta \gamma \Gamma E_e - I_b ). \label{eq:tiaVt} \tag{3}
$$

Equation $\eqref{eq:tiaVt}$ is further developed in the
[section for tuning](#tuning). 

### __Comparator circuit__

The comparator circuit transitions from analog to digital operation. 
Each of the $C_*$ comparators provides a digital output (1, 0) indicating if
its analog input $V_t$ is below or above its reference.  
The four digital outputs
($\overline{PARK}$, $\overline{BLU}$, $\overline{YEL}$, $\overline{RED}$)
indicate the target stripe alignments with 
individual cells.  As the [_mute cycler_](#mute-circuit) is causing
the transducer LEDs to flash at a high rate[^muterate], so each 
$V_t$ also pulses at that rate.  Thus when aligned with a stripe,
one of the outputs will provide a stream of 1's and 0's at the same rate.
This redundancy leads to high fidelity in the stripe counting stage
that follows.

{% include ghost.html
           img-dir=image-dir
           img-file='blockComparatorPath.svg'
           alt='schematic of Comparator circuit'
           caption='Comparator transition from Analog to Digital'
%}

The $V_{STRIPE}$ reference is set slightly below $V_r$ which triggers
$C_B$, $C_Y$ and $C_R$ when their corresponding cell aligns with a stripe.
The $V_{PARK}$ reference is set slightly above $V_r$ which triggers
$C_P$ when the $BLU$ cell aligns with the double stripe at the end of
the target.

Consider the piston at the PARK position; sitting on the bridge at the bottom
of its travel. Here the target double stripe is aligned with the 
$BLU$ cell.  Because the double stripe has $\Gamma^{park}$ the value
of $V_t^{B}$ exceeds $V_{PARK}$ and $V_{STRIPE}$ and triggers
both $C_P$ and $C_B$ outputs to low, pulsing the clock
input of the D-FlipFlop, $U_1$, and setting $Q$ high.  Simultaneously,
since the $YEL$ cell is _not_ aligned with a stripe, the $\overline{YEL}$
output of $C_Y$ is constantly high so the D-FlipFlop is not reset.  In this
state $U_2$ passes the pulsing $C_B$ output to $\overline{PARK}$.

As the piston rises above the double stripe the zone between stripes is
entered where no cell aligns with a stripe and $V_t$ is below $V_{STRIPE}$.
In this position, which is repeated between every stripe, all of the
four outputs,
($\overline{PARK}$, $\overline{BLU}$, $\overline{YEL}$, $\overline{RED}$),
are constant high levels.  No stripe position is detected.

As the piston continues to rise, the $Yel$ cell aligns with a stripe
causing $C_Y$ to pulse the $\overline{YEL}$ output.  These pulses
reset the D-FlipFlop which drives $\bar{Q}$ high and allows $U_3$,
subsequently, to pass $C_B$ to the $\overline{BLU}$ output
and inhibiting the $\overline{PARK}$ until the piston returns to
the PARK position.

Beyond this point, as long as the piston does not return to the PARK
position, each of the 
$\overline{BLU}$, $\overline{YEL}$ and $\overline{RED}$
outputs will pulse when their corresponding cell aligns with a stripe.

As the piston returns towards PARK there is a narrow moment where
$V_t^{B}$ is between $V_{STRIPE}$ and $V_{PARK}$ with $\overline{BLU}$
pulsing.  Continued piston falling from this position sets the D-FlipFlop,
activates $\overline{PARK}$, and restarts the overall cycle.
Should the piston not fall further the $\overline{BLU}$ correctly remains
active and the cycle does not restart.

{% include figure.html
           img-dir=image-dir
           img-file='clean_RedBrite_5.52_uno_50uS.png'
           alt='analog and digital signals at comparator'
           caption='Crossing the Analog to Digital boundary'
%}

Here is a snapshot of activity at the comparator stage. The yellow, blue and
red traces correspond to $V_t^Y$, $V_t^B$ and $V_t^R$ respectively.
The green trace corresponds to the $C_R$ output, $\overline{RED}$.
The target is positioned such that the 
*Red* cell is aligned at $\Gamma_{RED}^{stripe}$.  The mute cycler is running
at full speed for a 50 &micro;sec cell duration and is reported
by the 'scope as 43.378 &micro;sec (Width).

This image was collected prior to developing the full tuning algorithm
and there was some noise associated with the proto board layout so don't
look too critically at the numbers! The Top voltages reported by the
'scope are the noise peaks on the traces.  For the $V_t$ traces the center
line is at 3.3 volts.
The $C_R$ comparator output is centered at 2 volts.
At the time this image was collected 
I had not yet stumbled upon equation $\eqref{eq:snsVt1}$ and was tuning
for $V_t$ at $\Gamma^{stripe}$ of 5.5 volts with $V_{STRIPE}$ of 5.0 volts.

The majority of the image is consumed by a full round of the mute cycler:
From left to right first the *Blu* cell LED comes on at $t \approx 15{\mu}sec$
and shuts off $50{\mu}sec$ later at $t \approx 65{\mu}sec$.
Similarly, the *Yel* cell LED begins
its period at $t \approx 65{\mu}sec$ and the *Red* cell LED begins its period
at $t \approx 115{\mu}sec$.  The transimpedance amplifiers are always operating
so $V_t^B$, $V_t^Y$ and $V_t^R$ continuously indicate individual cell
irradiance $\Gamma^B E_e^B$, $\Gamma^Y E_e^Y$ and $\Gamma^R E_e^R$. 

Consider the blue $V_t^B$ trace.  When the $D_B$ comes on, at
$t = 20{\mu}sec$, $Q_B$ begins to conduct and $I_q^B$ reaches its 
final value $\approx 25{\mu}sec$ later[^muterate]. The maximum voltage
for $V_t^B$, 4.19 volts, never exceeds $V_{STRIPE}$ so the output of
comparator $C_B$ (not shown) remains high for the entire figure.

At $t = 65{\mu}sec$, $D_B$ shuts off, $D_Y$
comes on and $V_t^B$ settles around 1.8 volts.
At $t = 115{\mu}sec$, $D_Y$ shuts off, $D_R$
comes on and $V_t^B$ drops to its lowest value, the $OA_B$ lower rail
around 1.5 volt.
The resulting shoulder, that appears in all traces, is explained by
$E_e$ cross talk.  The *Yel* cell is adjacent to the *Blu* cell so
$D_Y$ spills into $Q_B$ a bit causing the shoulder.  The *Red*
cell is further away from the *Blu* cell so $D_R$ has less
effect on $Q_B$.  Note that the cross talk effect is different
for each of the cell pairs.  This is attributed to different orientations
and sensitivities of each of the individual components in the transducer.

The description of the yellow $V_t^Y$ trace for the *Yel* cell is similar to
that of the *Blu* cell.

For the red $V_t^R$ trace the situation is different as the *Red* cell
is aligned with a stripe.  Now, when $D_R$ comes on, the value of
$V_t^R$ settles around 5.1 volts which is higher than $V_{STRIPE}$.
This causes the output voltage of comparator $C_R$ to fall
at $t = 125{\mu}sec$ for about $40{\mu}sec$ constituting a single
Hi-Lo-Hi pulse of $\overline{RED}$.  These repeating $\overline{RED}$
pulses continue as long as the *Red* cell is aligned with a stripe.

### __Tooth circuit__

### __Analog circuit__

### __CAN circuit__

---
<br>

### __Tuning__

Substituting $E_e$ $\eqref{eq:ledEe}$, as developed for the drive circuit
into $V_t$ $\eqref{eq:tiaVt}$,
as developed for the TIA circuit, yields the primary design equation
for the sensor:

$$
V_t = R_t( {\kappa \alpha \beta \gamma \over R_e} \Gamma - {1\over R_b} ) V_d + V_r
\label{eq:snsVt1} \tag{4}
$$

which can be rearranged in $y = mx + b$ form, with variable $\Gamma$ as

$$
V_t = {\kappa \alpha \beta \gamma}{R_t \over R_e} \Gamma + ( V_r - {R_t \over R_b}  V_d).
\label{eq:snsVt2} \tag{5}
$$

<p style="text-align: center;" class="textFig">or</p>

$$
V_t = m_t\Gamma + b_t.
\label{eq:snsVtmb} \tag{6}
$$

In equations $\eqref{eq:snsVt1}$ and $\eqref{eq:snsVt2}$ the free values
are set as

- $V_r$ = 5 Volts chosen to set $V_{ce}$ and as a convenient reference

- $R_e$ = 1000 &Omega; chosen as convenient to monitor $V_e$ and appropriate
for the range of $I_e$

- $V_d$ = 2.5 Volts chosen to yield the desired range of $V_e$ given $R_e$.  

- $I_b = I_q{nom}$ = 1 mA as designated for the phototransistor

- $R_b = V_d / I_b$ = $2.5 V / 1 mA$ =  2500 &Omega; 

It is extremely convenient that the terms $\alpha \beta \gamma$ appear
as a single product. For each cell, this product collapses all of the 
LED and phototransistor specific variation into a single term which
can be considered as the cell gain.

The operation of tuning is to identify the circuit values of $\kappa$
and $R_t$ that balances the $I_q = I_b$ nominal operating point and
accounts for the $\alpha \beta \gamma$ cell gain in order to establish the
desired response of $V_t$ due to target movement induced changes to $\Gamma$.

The $\Gamma$ reflectance can be associated with several
readily identifiable target positions:

- $\Gamma^{dark}$ - the cell is centered on a dark region of the target

- $\Gamma^{stripe}$ - the cell is centered on a target stripe

- $\Gamma^{park}$ - the cell is near the double stripe at the target end

Prior to starting the tuning process, it is suggested to center all
potentiometers $R_d^{cell}$ and $R_t^{cell}$.  This will put the circuit into
a responsive pre-tune condition allowing for monitoring $V_t^{cell}$ as
adjustments are made.

The most important value of $V_t^{cell}$ will be used to determine the alignment
of a cell at $\Gamma_{stripe}$.  This voltage will be used by the
comparator circuit to detect stripe alignment.  In equation $\eqref{eq:snsVt1}$
it is seen that when
$({\kappa \alpha \beta \gamma \over R_e} \Gamma - {1\over R_b}) = 0$
that $V_t^{cell} = V_r$. Note that this
condition is independent of the value $R_t^{cell}$.

The _tuning mode_ is entered by holding the [_tune_ button](#mute-circuit)
while cycling power to the [Decode Circuit](#decode-circuit).
In this mode each transducer cell LED 
can be illuminated, one at a time, by successive presses of the _tune_
button. The [mute cycler](#mute-circuit) provides indicator LEDs that 
correspond to those in the sensor.

The tuning of $R_d^{cell}$ and $R_t^{cell}$ for each _cell_
proceeds by
selecting the _cell_ using the _tune_ button, and
connecting a voltmeter to $V_t^{cell}$:

1. Select the particular _cell_ (_Blu_, _Yel_ or _Red_) using the _tune_ button.
 
2. Connect the voltmeter to measure between $V_r^{cell}$ and $V_t$.
Move the middle of the target to a location where $V_t^{cell}$ reaches a peak
value.  This is a $\Gamma^{stripe}$ alignment.
Adjust $R_d^{cell}$ for 0 Volts measured, ($V_t = V_r^{cell}$).
This sets the $R_d^{cell}$ position, $\kappa^{cell}$.

3. **(This step needs work: $R_t$ adjust for voltage just above TIA low rail?
Possibly else and add TIA feedback diode? Setting gain based on
$\Gamma^{dark}$ seems arbitrary? )**
Connect the voltmeter to measure between $V_r^{cell}$ and $GND$.
Move the target by $1{1 \over 2}$ stripes to locate a local minimum.
This is a $\Gamma^{dark}$ alignment. Adjust $R_t^{cell}$ for 
**(~1.5v is low rail of tia)** 2? Volts measured.
This sets the $m_t^{cell}$ slope and $b_t^{cell}$ intercept per
equations $\eqref{eq:snsVt2}$ and $\eqref{eq:snsVtmb}$. 

4. Repeat for each of the _Blu_, _Yel_ and _Red_ cells.  After tuning, each cell
will yield $V_t^{cell} = V_r = 5 V$ when presented with $\Gamma^{stripe}$, and
$V_t^{cell} = 4 V$ when presented with $\Gamma^{dark}$.  Furthermore,
when presented with $\Gamma^{park}$, which occurs at the extreme end
of the target, the _Blu_ cell will produce a $V_t^{Blu}$ voltage somewhat
higher than 5 Volts.

---
<br>
See Also:


[SU Piston Position Calibration Fixture 7.2]({{ site.url | append: "/mini/project/su.piston.position/calib.7.2/calib.7.2-.html" }})

[SU Piston Position Guide Key]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/guideKey.7-.html" }})


---
<br>
Footnotes:

