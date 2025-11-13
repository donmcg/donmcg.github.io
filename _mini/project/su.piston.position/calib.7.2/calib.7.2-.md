---
layout: default
title: Calibration fixture 7.2
tip: calib.7.2 fixture
date:   2025-11-05 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position ] # applies to book level
  themes: [ calib.7.2 ] # applies to chapter level
---

# SU Piston Position Calibration Fixture for 7.2 design

Knowing the position of the piston along with the AFR, as the vehicle
is running, provides information to validate the needle profile.


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
           caption='<h2> Calib.7.2 fixture drawings </h2>
                    
                    Click to go there.'
%}


