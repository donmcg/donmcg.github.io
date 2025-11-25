---
layout: default
title: SU Piston Position Sensing
tip: SU piston position measurement
date:   2025-11-15 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: chapter # identifies presentation level of this file.
  topics: [ su.piston.position, measurement ] # applies to book level
  themes: [ SU Piston Position ] # applies to chapter level
---
Last update {{ page.date | date: "%d %b %Y" }}.

# SU Piston Position Sensing

> The modern mechanical carburettor is a highly developed
> device capable of accurately delivering the incorrect air/fuel mixture.

## SU Carburettor Principle of Operation

The basic principle of most carburettors, in *steady state*, is to sense the
throttle vacuum, controlled by the operator, in order to
regulate the AFR (air-fuel-ratio) of the mixture delivered to the engine.

For the SU steady state the throttle vacuum,
located in the region between the piston and throttle disc,
strongly influences the height of the piston above the jet.
A profile-tapered needle is affixed to the piston at one end
and passes through a fuel orifice at the other.  The diameter of the needle
varies along its length and its position in the orifice determines the amount
of fuel admitted to the air flow and
thus sets the mixture AFR based on the throttle demand.
All other operations of the SU that account for acceleration, deceleration, 
starting, temperature, power vs economy, etc are treated as deviations
from the steady state operation.

The carburettor 'knows' nothing about engine RPM or torque or horsepower.
It only senses the volume demand (pressure differential) and admits a specific
amount of fuel for that demand (with some modifications based on the dynamics of
the moment.)  Tuning an SU carburettor for a bespoke engine is first and
foremost about establishing the needle profile.  Thus it is essential
to be able to measure the needle position for any operating condition
so as to know where the profile is correct or needing adjustment. 

With the benefit of resources, a dynamometer provides a measure of
the torque and horsepower response of a particular needle profile over
various conditions of engine load and rpm.  But even with such an
advantage, it is necessary to know where the needle is positioned
so as to be able to effect appropriate modifications to its diameter and
achieve a given state of tune.  It is noted in passing that
knowing the position of the needle along with the AFR, as the vehicle
is running, also provides information to validate the needle profile.

Suffice it to say that tuning an SU-enabled engine amounts to identifying
a desirable needle profile as a primary step.  Such a needle may be provided
by substitution
from the array of available factory profiles.  And a given needle
profile can also be modified (polished) to suit a given installation.
Progress with this approach typically requires installing a needle,
measuring its behavior, then removing it for replacement or modification. 

As the needle of interest is constantly changing in this scenario, it
is common practice to associate needle position as an offset from
the piston position. The needle is installed with careful alignment in the
piston so as to establish a known profile offset.  Subsequently the piston
position measurement is used as a surrogate for the needle position.

The primary components of the SU system are illustrated below. 
Throttle vacuum on the left side of the **THROTTLE DISC** is communicated
to the chamber above the piston via 
the ***L-shaped Port*** (not labeled) in the base of the piston while
a ***Breather Tube Port*** (not drawn) admits atmosphere to the chamber below
the piston allowing the piston to rise.  The **PISTON SPRING** resists
this rise and forces the piston height to be in rough proportion to the
differential pressure presented by the two ports.
The **PISTON
UNIT** retains the **JET NEEDLE** which enters the **JET WITH HEAD** and
sets the amount of fuel admitted due to the piston height.

{% comment %}
   img-file='https://sucarb.co.uk/mediafiles/su/tech_su_04a.jpg'
{% endcomment %}

{% include figure.html
           img-file='https://sucarb.co.uk/mediafiles/su/tech_su_05a.jpg'
           alt='Drawing of H type carburettor'
           caption='H type carburettor'
%}


<br>
## Piston Position Sensing Throughout the Ages

Clearly the act of piston position measurement has always played a role
in developing needle profiles for an SU carburettor.  However historical
accounts this author has found do not provide much detail.  There
are [numerous references](https://sucarb.co.uk/catalogues-manuals-books/skinner-s-union-book.html) to owners' vehicles being delivered to
the SU factory for setup.  But no clear account of the methods used by the
factory.

Notable sites with general information:

- The [Burlen](https://sucarb.co.uk/technical) company is the present day
host for manufacturing and parts for the S.U and other components.
- The [Workshop Manual](https://sucarb.co.uk/catalogues-manuals-books/su-workshop-manual.html) 
is the definitive guide to S.U carburettors but gives little detail
for new applications.
- The [SU Carbs](https://www.mgb-stuff.org.uk/sucarbs.htm) provides considerable
detail regarding maintenance of these carburettors.
- This excellent [Video Series](https://www.youtube.com/channel/UCAhyT2zH_G0shbsGKG6rAkA )
provides a great deal of information about minis in
general and carburettion in particular. However it avoids details regarding
the piston height measurement.


Selected sites with anecdotal approaches:
- [Detecting S.U.piston lift](https://terryhunt.uk/tech/picsc/pics.htm)
provides detailed description of a tool for piston height measurement.
It also mentions another method but provides no further detail:
> ...use a stack of optical slot sensors with
> a vane that sits on the piston to drive LED's to display the position of the
> HIF piston at any point of drive...
- [SU Needle polishing](https://terryhunt.uk/tech/picsb/pics.htm ) Is a great
overview of the whole process of setting the needle profile.  It highlights
the 'conventional' piston height measurement using a calibrated rod
inserted into the damper well.
- [SU carb needle height position sensor POC](https://www.youtube.com/watch?v=pd_dfdJupMQ ) and [First Design SU Carb Needle Height Position Sensor](https://www.youtube.com/watch?v=cWcehaEgbLA )
uses a modified digital micrometer to measure piston height.  It also suggests
that it is possible to transmit the reading electronically. Nice.
- [SU Carb Needle Height Sensor](https://www.youtube.com/watch?v=yJjyA-RzAYk)
cleverly uses a magnetic angular position sensor for the desired measurement.
- [Antique PSW SU Carburetor Tool Set](https://offerup.com/item/detail/9d8b97dd-a0c3-3a47-a93a-01ce524a00c3) produced in West Germany is the closest thing
I have found to a standardized position measuring tool.  It relies on
a set of calibrated rods.

Reference publications:
- [The SU Carburettor High Performance Manual](https://books.google.com/books/about/The_SU_Carburettor_High_Performance_Manu.html?id=bNUjEQAAQBAJ ), 
by Des Hammill,
is the much referenced guide for developing an SU-bespoke marriage.  It also
covers many of the additional details that account for the non-steady-state
performance of the system.  As far as piston height is concerned it relies
on the calibrated rod.

- [Tuning BL's A-series engine](https://openlibrary.org/works/OL818220W/Tuning_BL's_A-series_engine?edition=key%3A/books/OL2070285M),
by David Vizard, is a must-read for any British A-series engine enthusiast.
While it does cover the standard procedure for needle profiling, when it comes
to piston height, my 2nd Edition simply says:
> ...check how much the carb is open...  

  Which certainly gets to the point but is not very helpful!


All of the above approaches rely on removing the damper assembly and
replacing it with some kind of sensor.  They have the great advantage of
being able to be reused easily on different cars. They are also appropriate
for *steady state* measurements, presumably taken in the garage, but
would perhaps limit the normal operation of the vehicle in that the damper
is completely disabled.


<br>
## What does AI say?

I have to admit that AI generates a nice overview of the process!  It
does not help any with the actual piston height measurement.
Note the emphasis, seen throughout the literature, with using
AFR as the indicator of tuning...

**Query:**
How does the factory develop a new SU needle profile
for a bespoke engine? 

**Answer:**
> Developing a new SU carburetor needle profile for a bespoke engine is an
> empirical process involving extensive testing and refinement on an engine
> dynamometer and through road testing. The factory approach uses specialized
> equipment and expertise to achieve the optimal air-fuel ratio across all
> engine operating conditions.
> 
> ### Development Process
> 1. Initial Engine Characterization: The engine is first tuned for all
> conditions on a test dynamometer using variable (hand-controlled) mixture
> settings. This helps determine the effects of engine specifics like camshaft,
> ignition timing, manifold design, and exhaust systems.
> 
> 2. Data Collection on Dynamometer: Once the engine particulars are finalized,
> serious carburetion tuning begins. The engine is run under various steady-state
> and variable load conditions, with exhaust gas analyzers (AFR meters) 
> monitoring the air-fuel ratio (AFR).
> 
> 3. Identifying Rich/Lean Areas: Data is collected at different engine speeds
> and throttle positions to identify where the mixture is too rich or too lean.
> The needle's diameter at specific points along its length determines the 
> mixture strength at corresponding piston lifts (which relate to airflow/engine
> load).
> 
> 4. Needle Profiling: Based on the dynamometer readings, the needle's profile
> is adjusted by removing material (making it thinner) in specific areas to 
> richen the mixture, or by selecting a fatter needle to lean it out. This is
> a meticulous, iterative process done in small steps (e.g., 0.001" or 0.002"
> changes in diameter).
> 
> 5. Prototyping: A prototype needle is created based on the modified dimensions.
> In a factory setting, once the optimum dimensions are found, a profile cam
> is made to ensure accurate reproduction of the desired shape for production
> needles.
> 
> 6. Verification and Road Testing: The new needle is installed, and the engine
> is re-tested on the dynamometer and then in the actual vehicle through
> extensive road tests. This ensures the correct mixture is maintained through
> the full operating range, including cold starts and various climatic
> conditions.
> 
> 7. Finalization: The process is repeated until the mixture is optimal
> (typically an AFR of 12:1 to 11.5:1 at full power) and performance and
> fuel consumption targets are met. 
> 
> ### Key Tool
> The primary tool for this process is an engine or chassis dynamometer
> equipped with an exhaust gas analyzer to monitor the air-fuel ratio
> in real-time. 

**Query:** How does the factory measure piston position when developing a new SU needle profile for a bespoke engine? 

**Answer:**

> When developing a new SU needle profile for a bespoke engine, engineers need
> to know the piston's position at various engine speeds and loads to correlate
> it with the required air-fuel mixture. The factory or development teams use a
> couple of primary methods for this: a simple mechanical indicator rod or a
> more sophisticated manometer system. 
> 
> ### Mechanical Indicator Rod 
> 
> This method involves a physical modification to the carburetor: 
> - A small, vertical hole is drilled through the top of the suction chamber
> cap.
> - A slim rod (often made of a soft metal like solder or a pencil lead to
> prevent damage) is inserted through this hole to rest on the top of the
> piston.
> - The rod is cut off flush with the top of the cap when the piston is at its
> lowest point (resting on the bridge of the carburetor).
> - As the engine runs and the piston rises with increased airflow, the rod is
> lifted.
> - The extent of the piston lift can be measured at different engine operating
> conditions (RPM, throttle position) using a ruler or a depth gauge.
> - This method provides a direct, albeit manual, measurement of piston lift.
> Care must be taken to ensure the rod moves freely and an adequate seal is
> maintained with a little oil to prevent a vacuum leak, which would affect the
> reading. 
> 
> ### Manometer System 
> A more advanced and continuous measurement method involves using a manometer: 
> - One side of the manometer (using a liquid of low specific gravity, like
> paraffin) is connected by a small-bore tube to the air chamber above the
> piston (via the damper cap hole).
> - Movement of the piston displaces the air in the tube, which in turn moves
> the liquid in the manometer, providing a visual indication of piston lift.
> - The bore of the glass tube can be selected to magnify the movement for
> easier reading.
> - This setup can be monitored during road testing or on a rolling road
> dynomometer to record piston positions across a full range of engine operating
> conditions.
> - An external valve in the air tube allows the instrument to be "zeroed" at
> any time by momentarily opening the valve when the piston is resting on the
> bridge (accelerator released). 
> 
> ### Data Analysis and Profiling
> The measurements obtained from these methods allow engineers to determine the
> exact vertical position of the piston (and thus the corresponding station on
> the tapered needle) for various engine demands. This data is then correlated
> with exhaust gas analysis (using a wideband lambda sensor) to ensure the
> air-fuel ratio is optimal across the entire operating range, allowing for the
> precise grinding or manufacturing of a bespoke needle profile. The entire
> process often involves extensive trial and error on a rolling road 
> dynomometer. 

The AI result does reveal the manometer as an alternative approach
to measuring the piston position.  However it is indirect in that
the manometer reading itself must be cross-calibrated to the piston position.
In addition, it is not entirely clear how to access the chamber above the
piston without altering or damaging the carburettor in question.  (Perhaps
a solid state absolute pressure transducer could be mounted inside the bell
chamber above the piston with wiring exiting through a drilled and sealed
hole?)

<br>
## The Fairhillbillies SU Piston Position Sensor

An alternative position sensing scheme, first proposed here, is the
[Fairhillbillies SU Piston Position Sensor]({{ site.url | append: "/mini/project/su.piston.position/su.piston.position-fairhillbillies.html" }} ).
This approach does require (reversible) modification of the carburettor.
However the modification does not otherwise impact the operation of the
carburettor and can be left in place for the life of the vehicle.
Once in place it provides the ability to continuously monitor the piston
position and to transmit that data for further processing.
Coupled with an on-board AFR meter, to a large degree,
the open road replaces the need for a dynamometer to establish
the needle profile for a bespoke engine.


<br>
## Other SU Piston Position Sensor Ideas

A number of alternative position sensing schemes are reviewed at
[Other SU Piston Position Sensor Ideas]({{ site.url | append: "/mini/project/su.piston.position/su.piston.position-other.html" }} ).
These all have pros and cons, as does the chosen method.
