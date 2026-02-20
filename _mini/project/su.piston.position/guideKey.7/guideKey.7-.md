---
layout: default
title: Guide Key 7
tip: guide key for su position sensor 7 series
date:   2026-02-08 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.


{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/
{% endcapture %}

# SU Piston Position Guide Key 

Here's a drawing of the standard guide key from an HIF6. It features an 
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
piston groove. There are two approaches to claim that space for 
the transducer:

1. The first is to fit the transducer into a groove cut in the
tongue face of the guide key, adjacent to the piston.
Available space for the transducer
is extremely limited. The sensor can route upwards across the top of
the anchor, or can route downward and out the carburettor throat.
This approach reduces the strength of the guide key. 

    This is the approach that was taken with sensor 4 and 5 series designs.
The routing of the sensor above the anchor is somewhat difficult, as the
connecting wires have to route through the piston breather tubes.  But 
the real problem is simply making space for the transducer in the same
area as the standard tongue.

2. The second is to move the tongue of the key upward so as to provide room
for the transducer in the area formerly occupied by the tongue tip.

    This is the approach that was taken with sensor 7 series designs.
The routing of the sensor exits via the carburettor throat as there
is no simple way to exit via the breather tubes. (This may be revisited
in a future sensor version.)

The remainder of this document describes the guide key to be used
with sensor 7 series.

# SU Piston Position Guide Key 7

Guide Key 7 is designed to mate with the 7 series of sensors. 

Here's a view of newKey.4.  This drawing is intended to assist with
the setup and direction of milling operations as described by the
[New Key Milling Procedure V4]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/newKeyMachining.7.4-.html" }}) .

{% include figure.html
           img-dir=image-dir
           img-file='newKey.4.1.png'
           alt='Drawing of new guide key'
           caption='New Guide Key 7, rev 4'
%}

The 7 series sensor design is intended to address issues with crosstalk
between the three transducer cells. 

- [ ] ToDo:
> put a link to the transducer section here

As such there is a one-cell-wide space between each of the cells.  This 
makes the 7 series transducer occupy five cell heights on the sensor.
This total height of transducer is accommodated by by newKey.4.
As such, the tongue tip height for newKey.4 is reduced to 100 mil from the 
standard key height of 190 mil.

> Note that the 7 series transducer did improve crosstalk, but did not
> eliminate it. 
> However, it led to the development of muting, which eliminates crosstalk
> altogether. Potentially a future transducer could be reduced in height 
> by placing
> the cells directly adjacent to each other.  This would provide an
> additional 80 mils for the new tongue height.

---
<br>
See Also:

[New Key Milling Procedure V4]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/newKeyMachining.7.4-.html" }})



