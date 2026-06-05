---
layout: default
title: Calibration Fixture
tip: calibration fixtures for su position sensors
date:   2026-06-05 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position ] # applies to book level
  themes: [ calibFix ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.


{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/calibFixture/
{% endcapture %}

# SU Piston Position Calibration Fixture 

## Log: [Series 7 Calibration Fixture]({{ site.url | append: "/mini/project/su.piston.position/calibFixture/series-7-calibfix-blog.html" }})
## Log: [Series 8 Calibration Fixture]({{ site.url | append: "/mini/project/su.piston.position/calibFixture/series-8-calibfix-blog.html" }})

Here's a drawing of the standard guide key from an HIF6/HIF44. It features an 
anchor with a beveled hole for a countersink head screw and a tongue
which bends at a right angle.

{% include figure.html
           img-dir=image-dir
           img-file='guideKey.1.1.png'
           alt='Drawing of original guide key'
           caption='Original Standard Imperial Guide Key'
%}

The tip of the tongue is wide and
fits, with minimal clearance, into the piston groove.
This prevents the piston from rotating about the axis of the needle.

{% include figure.html
           img-dir=image-dir
           img-file='guideKey_in_piston.png'
           alt='Drawing of original guide key fitted in piston'
           caption='Standard Guide Key fitted to Piston Groove'
%}

With this design the standard tongue fills the available space in the
piston groove. There are several approaches to claim that space for 
the transducer, all of which require a modification to the guide key:

1. Fit the transducer into a groove cut in the
tongue face of the guide key, adjacent to the piston.
Available space for the transducer
is extremely limited. The sensor can route upwards across the top of
the anchor, or can route downward and out the carburettor throat.
This approach reduces the strength of the guide key. 

    This is the approach that was taken with sensor series 4 and 5 designs.
The routing of the sensor above the anchor is somewhat difficult, as the
connecting wires have to route through the piston breather tubes.  But 
the real problem is simply making space for the transducer in the same
area as the standard tongue.

    No guide key was ever developed for these designs.

2. Move the tongue of the key upward so as to provide room
for the transducer in the area formerly occupied by the tongue tip.

    This is the approach that was taken with sensor 7 series designs.
The routing of the sensor exits via the carburettor throat as there
is no simple way to exit via the breather tubes. (This may be revisited
in a future sensor version.)

    The sensor series 7 was sucessful and provided several insights:
    * The guide key tongue engagement with the piston is limited and 
      substantially less than the original guide key.
    * It is imperative to operate the sensor cells one-at-a-time: in spite
    of the 1/12" spacing, there is too much crosstalk between cells to have
    all LEDs illuminated simultaneously.
    * Installation of the sensor in the carb throat is troublesome. 
    Advanced adhesives seem to be required for the gasoline-rich environment.

3. Move the tongue of the key upward and extend above the heel so as to provide room
for a minimum space sensor and retain full engagement of the tongue in the piston.

    This is the approach that was taken for the sensor 8 series designs.
The routing of the sensor exits via the breather tubes.  The flex sensor is 
extended in length to avoid the need for a cable blocking the breather tube.  
Connection to a stay board is similar to the sensor 7 series.

## SU Piston Position Guide Key for sensor series 7

Revision numbers for guide key designs do not track with the sensor series numbers.
newKey.4 is designed to mate with the 7 series of sensors. 

Here's a view of newKey.4.1 as used in conjunction with 3p_sensor_7.2:

{% include figure.html
           img-dir=image-dir
           img-file='series-7/newKey.4.1.png'
           alt='Drawing of new guide key'
           caption='Series 7 Guide Key'
%}

The series 7 sensor design is intended to address issues with crosstalk
between the three transducer cells. It features three cells, each containing
an individually driven photocell and LED.

- [ ] ToDo:
> put a link to the series 7 transducer section here

For series 7 there is a one-cell-wide space between each of the cells.  This 
makes the 7 series transducer occupy five cell heights on the sensor.
This total height of transducer is accommodated by by newKey.4.
As such, the tongue tip height for newKey.4 is reduced to 100 mil from the 
standard key height of 190 mil.

Here the sensor is mounted entirely on the carburettor body and the guide key is 
screwed in place later.  The long transducer fills the available space below
the guide key and is routed out of the carburettor throat.  This places much of
the sensor in the region of air flow.

{% include figure.html
           img-dir=image-dir
           img-file='series-7/AnchorArchKey-comp.png'
           alt='Drawing of series 7 guide key and transducer'
           caption='Series 7 Transducer mounted on carburettor body (not shown)'
%}

> Note that the 7 series transducer did improve crosstalk, but did not
> eliminate it. 
> However, it led to the development of muting, which eliminates crosstalk
> altogether. Potentially a future transducer could be reduced in height 
> by placing
> the cells directly adjacent to each other.  This would provide an
> additional 80 mils for the new tongue height.

## SU Piston Position Guide Key for sensor series 8

Revision numbers for guide key designs do not track with the sensor series numbers.
BrassKey10 is designed to mate with the 8 series of sensors. 

Here's a view of brassKey.10.3 as used in conjunction with 3p_sensor_8.4:

{% include figure.html
           img-dir=image-dir
           img-file='series-8/brassKey1-comp.png'
           alt='Drawing of series 8 guide key'
           caption='Series 8 Guide Key'
%}

The series 8 sensor design is intended to minimize the transducer footprint
and so make better use of the limited available space.  It allows for the permanent
mating of the sensor and guide key and simplifies assembly in the carburettor body.

- [ ] ToDo:
> put a link to the series 8 transducer section here

Series 8 eliminates cross-talk by operating one-cell-at-a-time.
The one-cell-wide space between each of the cells of series 7 is eliminated and
makes the series 8 transducer occupy only three cell heights on the sensor.
This small transducer can be mounted as a cantilever bonded to the guide key tongue.
The result is a single assembly that can be much more easily installed in the carburettor.

{% include figure.html
           img-dir=image-dir
           img-file='series-8/KeyAnchorHeel-comp.png'
           alt='Drawing of series 8 guide key and transducer'
           caption='Series 8 Transducer mounted on Guide Key'
%}

---
<br>
See Also:

[Series 7 Guide Key Machining]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-7-guidekey-blog.html" }})

[Series 8 Guide Key Machining]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-8-guidekey-blog.html" }})
