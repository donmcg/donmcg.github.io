---
layout: page
title: Calibration fixture 7.2 drawings
tip: drawings of calib.7.2
date:   2025-11-28 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: page # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ calib.7.2 ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.

{% assign image = site.url | append: "/assets/mini/project/su.piston.position/calib.7.2/" %}
{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/calib.7.2/
{% endcapture %}

# SU Piston Position Calibration Fixture for 7.2 design

Construction projects that require even a minor degree of precision
benefit from scaled drawings for fit and assembly.  These are drawings
for the calib_7.2 fixture.

---
<br>
### 3p_sensor_7.2 flex sheet

Here is a drawing of the flex sheet as it comes from the assembly house. The
sheet is about 3 mil thick and highly flexible.  The sensor, shown in green,
is connected to the sheet in a few locations that must be cut to remove
the sensor from the sheet.  The sensor is left attached for this fixture.

The active portion of the sensor is represented by the blue blocks at
the bottom center of the drawing.  Adjacent to the sensor is a hole
for anchoring in the body of the carb.  

Electrical contacts are outlined at the end of the flare at the top center
of the drawing. The pads are on the backside of the sensor and not visible.  

{% include figure.html
           img-dir=image-dir
           img-file='assy.3p_flex.png'
           alt='Drawing of 3p_sensor_7.2 flex sheet'
           caption='3p_sensor_7.2 flex sheet'
%}


<br>
### 3p_target_7.2 fr4 board

This drawing of the target shows the fr4 board, in green, with the white 
silkscreen pattern 'teeth'.  The spacing of the pattern provides a resolution
of 24 positions per inch (i.e. 3 positions per 1/8 inch).  At one end
the double tooth pattern is seen which is used to establish the 'park'
position of the piston.

The actual target fr4 board is black rather than green so as to maximize
the variation in reflected light as the white pattern moves.

Such target will be mounted in the piston groove of the carburettor.

{% include figure.html
           img-dir=image-dir
           img-file='target24tpi.png'
           alt='Drawing of 3p_target_7.2 fr4 board'
           caption='3p_target_7.2 fr4 board'
%}


<br>
### Target carrier assembly

For this fixture, a representative target is mounted in a carrier
which makes handling and alignment much easier.

The carrier is made with 60 mil perforated board.  A 15 mil deep channel
is machined to establish the correct target-sensor spacing. The target
is attached to the carrier using the same double-sided tape as used
to mount the target on the piston.

The carrier assembly will be flipped over from the orientation in this view
when placed on top of the overlay plate.

{% include figure.html
           img-dir=image-dir
           img-file='assy.target.png'
           alt='Drawing of target carrier assembly'
           caption='Target carrier assembly'
%}


<br>
### Pogo pin assembly

Electrical contacts to the sensor pads are made with pogo pins.  These
spring loaded pins are mounted on a plated-hole perf board.

The pogo assembly mounts directly in the base plate and
includes screws and springs that allow for setting the correct 
pogo compression with the sensor pads. 

Not shown is the wiring which exits through the backside of the base plate.

{% include figure.html
           img-dir=image-dir
           img-file='assy.pogo.png'
           alt='Drawing of pogo pin assembly'
           caption='Pogo pin assembly'
%}


<br>
### Calib.7.2 fixture

This is a view of the assembled fixture.

The overlay plate, in green, is fabricated from 60 mil perf board and is
machined with a groove and an opening.

A guide for the target carrier, in blue, made from 60 mil perf board
is affixed to the overlay plate, using generic ouble-sided tape,
so as to maintain the alignment of
the target over the sensor as the carrier is moved laterally.

The overlay plate is retained by a clamp, in brown.  In addition, a
second clamp, in magenta, ensures proper compression of the pogo pins.

{% include figure.html
           img-dir=image-dir
           img-file='assy.calib.7.2.png'
           alt='Drawing of calib.7.2 fixture'
           caption='Calib.7.2 fixture'
%}


<br>
### Calib.7.2 fixture without overlay plate

This view hides the overlay plate and carrier in order to show the sensor
flex sheet.  

{% include figure.html
           img-dir=image-dir
           img-file='assy.see.3p.png'
           alt='Drawing of calib.7.2 fixture without overlay plate'
           caption='Calib.7.2 fixture without overlay plate'
%}

<br>
### Calib.7.2 fixture assembly

Here's a photograph of the completed fixture.

{% include figure.html
           img-dir=image-dir
           img-file='small_calib_7.2_assy.jpeg'
           alt='Photograph of calib.7.2 fixture without carrier'
           caption='Calib.7.2 fixture without carrier'
%}

<br>
### Calib.7.2 sensor 

Here's a close up of the sensor area.

{% include figure.html
           img-dir=image-dir
           img-file='calib_7.2_sensor.jpeg'
           alt='Photograph of calib.7.2 fixture sensor area'
           caption='Calib.7.2 fixture sensor area'
%}

The black rectangles are the phototransistors.  Directly above each
phototransistor is its associated infrared LED.  The flex PCB can be
seen below the active devices.  R Y B refers to the position of the 
Red, Yellow, and Blue channels.

<br>
### Calib.7.2 fixture with micrometer

Here's a photograph of the fixture with the micrometer positioning 
assembly added.

{% include figure.html
           img-dir=image-dir
           img-file='small_calib_7.2_with_micrometer.jpeg'
           alt='Photograph of calib.7.2 fixture with micrometer'
           caption='Calib.7.2 fixture with micrometer'
%}

The X-micrometer, to the left, provides position adjustment and measurement
at 1-mil increments.  The total travel is 1/2-inches.  This travel is
less than that of the piston itself, but is more than adequate for 
development of the system.  Adjustment of the micrometer is quite smooth
and satisfying.

{% comment %}
<!-- these images are not needed -->
![Closeup drawing of flex sensor]({{ image }}assy.see.3p.sensor.png "3p_sensor_7.2 close")

![layer1]({{ image }}assy.layer.1.png)

![layer2]({{ image }}assy.layer.2.png)

![layer2]({{ image }}assy.layer.4.png)

![layer2]({{ image }}assy.layer.7.png)
{% endcomment %}

