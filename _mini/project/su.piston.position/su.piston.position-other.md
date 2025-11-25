---
layout: default
title: Other SU Piston Position Sensor Ideas
tip: Other SU piston position sensor ideas
date:   2025-11-16 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position, measurement ] # applies to book level
  themes: [ SU Piston Position ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.

Before settling on the approach of the 
[Fairhillbillies SU Piston Position Sensor]({{ site.url | append: "/mini/project/su.piston.position/su.piston.position-fairhillbillies.html" }} ),
several other sensor concepts were evaluated.

* Reflected Light:
  Inspired by Vizard's "check how much the carb is open" suggestion
  this would place an IR LED and Phototransistor so as to monitor the
  light reflected by the exposed portion of the piston as seen looking
  into the carburettor throat.  Perhaps the piston groove would be
  painted with a highly reflective material to facilitate the contrast
  between the extremes of piston travel.  
  * Pros:
    * Fairly simple and cheap sensor arrangement.

  * Cons:
    * Pure analog approach subject to high variability due to 
    temperature, aging, contamination, etc.
    * Difficult to maintain calibration.

<br>
* [Magnetopot](https://www.digikey.com/en/product-highlight/s/spectra-symbol/magnetopot-potentiometers)
contactless sensors detect the location of a magnet positioned near a sensor
element.
  * Pros:
    * Contactless sensing would not adversely affect normal piston operation. 
    * Good calibration and repeatability.

  * Cons:
    * Available configurations are difficult to incorporate within 
    the working envelope of the carburettor.

<br>
* Resistance Potentiometer: Rig a resistive bar, perhaps in the piston groove
and add a sliding contact near the guide key.
  * Pros:
    * Could probably be made to fit.
    * Good calibration and repeatability.

  * Cons:
    * Sliding contact might inhibit piston operation.
    * Difficult to establish electrical connection to the portion of the
    circuit contained in the piston without altering the carburettor.  

<br>
* TMR (Tunnel Magneto Restrictive) sensor: Detect the changing magnetic field
of a alternating magnet strip; count the alternations to establish position.
In particular the
[TLI5590 - A6W](https://www.digikey.com/en/products/detail/infineon-technologies/TLI5590A6WXTMA1/16730908?s=N4IgTCBcDaIC4BsCWBWFBOADCAugXyA)
device is a wafer-level solder-ball device that is exceptionally small and
would fit well in the area around the SU guide key.  The alternating
magnet strip would be located in the piston groove.
  * Pros:
    * Could probably be made to fit.
    * Good calibration and repeatability.

  * Cons:
    * Alternating permanent magnet strip to fit piston groove may not
    be feasible or may be a special order item.
    * Electromagnet alternative would fit the space but would likely
    produce a B-field only half of what is needed for the full range
    of sensitivity.
    * Difficult to establish electrical connection to the portion of the
    circuit contained in the piston without altering the carburettor. 
    * The TLI5590 is already end of life although parts are still available.

<br>
* [MAP (Manifold Air Pressure)](https://www.mouser.com/new/infineon/infineon-kp215f1701-map-2go-kit/)
type sensor: The electronic version of a manometer.  This would sense the 
pressure inside the chamber above the piston and use that to infer the 
piston height.  A slight alternative would be to sense the pressure
behind the throttle plate by accessing through the breather tube of the SU.
  * Pros:
    * Could probably be made to fit.

  * Cons:
    * Challenging calibration and repeatability.
    * Probably adversely affected by dynamics of acceleration,
    temperature, etc.
    * Potentially needs to irreversibly modify the carburettor.

<br>
* Capacitance sensor: could take a variety of forms.  The idea is to 
split the capacitor plates placing half on the piston and the other
at the guide key such that
a variable capacitance is formed.  This could take a number of different forms.
The sensing result could be pure continuous or a counting of passing features.
After some study it was concluded that the constraints of space lead
to small area sensor capacitor plates with relatively large dielectric
thickness.  This leads to very small capacitor values and the need for
high frequency excitation, perhaps in the GHz region.  Approaches
in systems employing similar principles, such as for
[buried servo capacitive position error detection](https://ieeexplore.ieee.org/abstract/document/1061693)
demonstrate the feasibility of the approach.
  * Pros:
    * Could probably be made to fit.
    * Potentially no circuitry on piston requiring external electrical
    connection.
    * Potentially simple calibration (counter).

  * Cons:
    * Difficult geometry for sensor.  Must be developed.
    * Introduces RF signals into the system; compliance requirements.
    * Potentially challenging calibration and repeatability (continuous).

<br>
* Inductance sensor: Somehow use coils surrounding the (non-magnetic) piston
chamber to detect the height of the (partially iron) piston assembly.
It is to be admitted that this author could not come up with a method
to do this.  Presumably it would require RF excitation of some sort.
  * Pros:
    * It would be cool.

  * Cons:
    * Unknown how to implement a feasible scheme.

