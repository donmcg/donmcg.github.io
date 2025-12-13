---
layout: default
title: Calibration fixture 7.2
tip: calib.7.2 fixture
date:   2025-11-28 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position ] # applies to book level
  themes: [ calib.7.2 ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.

# SU Piston Position Calibration Fixture for 7.2 design

Knowing the position of the piston along with the AFR, as the vehicle
is running, provides information to validate the needle profile.

After initial characterization of a few sensors it has become evident
that there is significant variation in both phototransistor beta 
and in the optical loss of the led-target-phototransistor path.
Hence the detector design will be improved if these variations are
accounted for.

The initial fixture for these kind of measurements provides excellent
resolution of x-z positioning of the sensor to target, but is awkward
in assembly and requires removing the flex sensor from its sheet
and making solder connections.  While not insurmountable, these are 
destructive steps and do not scale well to evaluating multiple sensors.

The calib.7.2 fixture is intended to overcome some of these limitations.
With it the sensor does not need to be removed from its sheet, no solder
connections are needed, and the optical path closely resembles in-situ.
In addition, the target is able to move through its entire range.
When coupled to the existing x-z fixture the target position can be
measured with a micrometer.

The 3p_sensor_7.2 device is produced on a flex pcb and loaded with its
led and phototransistor components at the pcb fab house. Conveniently,
the sensor is not removed from the larger rectangular sheet of flex material
which makes handling much easier.  The sensor is attached to the larger
sheet at only a few locations and is easily separated when the time comes.

The mechanical components are all produced from common materials available
at local hardware and lumber yards. The electronic components are sourced
from a well known on-line dealer.

Construction of the calib_7.2 fixture begins with a 3/4" birch plywood base
plate upon which subsequent components are stacked.  This piece was
cut on a table saw and machined on a router table and drill press.
It provides mounting support for the remaining components and is static safe.

A pogo pin assembly is constructed from 0.1" perforated
and plated breadboard, pogo pins, screws, springs and ribbon cable. 
When installed, the spring-loaded screws provide a means to set the
height of the pogo pins such that proper contact is made with the
pads of the flex board.

The base plate carries the pogo pin assembly.
The backside of the base plate is routed for the ribbon cable.  Clearance
holes for pogo-pin assembly nuts are machined along with holes for
clamp bolts.

An overlay plate, made from non-plated 0.1" perf board, lays on top of the
flex sheet and provides an opening for the sensor and a clearance channel
for the target.

The target carrier, made from non-plated 0.1" perf board, retains the
target in its own channel and provides
the means to align and shift the target above the sensor.  The channels
in the target carrier and overlay are set to provide a target-sensor
spacing similar to that when installed in the carburettor.

A perf-board straight-edge guide for the target carrier mounts on the 
overlay plate.  The overlay plate and flex board stack-up is secured
in place with a hardwood clamp, 1/4" screws and wingnuts. An additional
wood clamp, aligned with the pogo pin -- flex board interface,
is similarly made.

---

{% assign image-dir = site.url | append: "/assets/mini/project/su.piston.position/calib.7.2/" %}
{% capture link-dir %}
  {{site.url}}/mini/project/su.piston.position/calib.7.2/
{% endcapture %}

{% include img_cap_link.html
           img-dir=image-dir
           img-file='assy.calib.7.2.png'
           alt='drawing of calib.7.2 fixture'
           link-dir=link-dir
           link-file='fixture.drawing.html'
           caption='<h2> Calib.7.2 fixture component drawings </h2>
                    
                    Click to go there.'
%}

---

<br>
A second base plate is fabricated from 3/4" ply and is constructed
so as to capture the calib_7.2 and x-y fixtures in alignment.
A pair of removable shims hold the two fixtures together.

A thin aluminum sheet is cut 1" wide and forms a coupling arm
bewteen the x-micrometer and the target carrier.  The arm is
slightly bent so as to form a spring that, along with double-sided tape,
marries the micrometer to the carrier.



