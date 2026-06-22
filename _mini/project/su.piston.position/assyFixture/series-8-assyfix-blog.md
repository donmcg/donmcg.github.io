---
layout: default
title: Assembly Fixture for series 8 sensors and guide keys
tip: instructions for producing assembly fixture for series 8
date:   2026-06-05 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
# level: chapter # identifies presentation level of this file.
  level: page # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ assyFix.8 ] # applies to chapter level
---

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/assyFixture/series-8/
{% endcapture %}
{% capture key-image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/
{% endcapture %}

## Series 8 Assembly Fixture

The assembly fixture provides for the bonding of the sensor to the guide key.

<ol>
  {%- include binder_tome_blog_list.html sitecoll=site.mini tome="project" blog="project/su.piston.position/assyFixture/series-8-assyfix" gab=false order='reverse' -%}
</ol>

<br>

{% include figure.html
           img-dir=image-dir
           img-file='assyFixture.8-comp.png'
           alt='series 8 assembly fixture'
           caption='Series 8 Assembly Fixture'
%}

A series 8 sensor and guide key are bonded with adhesive to form a single unit
for installation in the HIF6/HIF44 carburettor body:

{% include figure.html
           img-dir=key-image-dir
           img-file='KeyAnchorHeel-comp.png'
           alt='series 8 sensor bonded to guide key'
           caption='Series 8 Sensor Bonded to Guide Key'
%}
The sensor's extended lanyard section is not shown in the image above.

The assembly fixture in action:

{% include figure.html
           img-dir=image-dir
           img-file='assyAction-comp.png'
           alt='series 8 assembly fixture in use'
           caption='Series 8 Assembly Fixture Close Up'
%}

<br>

## Here is a breakdown of the components:

1. Floor

   The floor base plate is constructed from 3/4" hardwood plywood.
   ![]({{image-dir}}Floor/Floor.8-comp.png)

2. Pedestal

   The pedestal is constructed from poplar milled to 5/8" thickness.
   It provides support for the sensor and aligns it to be flush with the anvil.

   ![]({{image-dir}}Pedestal/PedestalSensor-comp.png)

3. Base

   The base is machined from 5/16" square brass.
   It provides support and alignment for the brass and flexPCB components.

   ![]({{image-dir}}Base/BasePinScrew-comp.png)

4. Anvil

   The anvil is machined from 5/16" square brass.
   It provides support and alignment for the flexPCB sensor and guide key.
   A shim is located at one end to fill space and establish the 
   correct angle for the flexPCB.

   ![]({{image-dir}}Anvil/AnvilShim-comp.png)

5. Sensor

   The sensor assembly is a flexible PCB with the transducer cells at one end 
   and a connector at the other. For assembly, the sensor is removed from the flex
   sheet. The sensor lays on top of the pedestal and 
   the anvil and is located by a pin that extends up from the base, through the anvil.

   The peculiar shape of the sensor at the connector end arises from the need to 
   route the wide end through the vent hole of the carburettor body.

   ![]({{image-dir}}Sensor/Sensor-comp.png)

   Here is a close up of the transducer area of the sensor.  The assembly fixture 
   will bend it to this shape and bond it to the guide key.

   ![]({{image-dir}}Sensor/BentSensor-comp.png)

6. Key

   The guide key is machined from 5/16" square brass.
   It sits on top of the sensor in the fixture.

   ![]({{key-image-dir}}guideKey-8-comp.png)

7. Ram

   The ram is machined from 5/16" square brass.
   It compresses the guide key and sensor into contact with each other.
   A thumb screw is used to provide the compressive force.

   ![]({{image-dir}}Ram/Ram.8-comp.png)

8. Bolster

   The bolster is machined from 5/16" square brass and fitted with a compliant pad.
   It forces the bend of the sensor to be parallel to the cantilever on the 
   rear of the guide key tongue.

   ![]({{image-dir}}Bolster/BolsterPad-comp.png)

9. Guide

   Two guides allow the bolster to slide into place so the sensor can 
   be bonded to the guide key.

   ![]({{image-dir}}Guide/Guide.8-comp.png)

<br>

---
<br>

## Bonding 

TBD!

---


<br>

The milling operations are performed on a
[Sherline 5400](https://www.sherline.com/product/54005410-deluxe-mill/#instructions) mill.

Other tools included standard table saw, drill press, etc. 

<br>

{% comment %}
#### Some interesting links:

[Sherline 5400](https://www.sherline.com/product/54005410-deluxe-mill/#instructions) 12" Deluxe Mill

[]()

{% endcomment %}

