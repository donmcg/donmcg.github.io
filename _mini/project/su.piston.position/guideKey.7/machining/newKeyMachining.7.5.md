---
layout: default
title: Rev.5 Guide Key 7 Machining Procedure
tip: machining guide key 7, rev 5
date:   2026-03-25 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
  blog: prddoject/su.piston.position/guideKey.7/machining
---

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/
{% endcapture %}

Last update {{ page.date | date: "%d %b %Y" }}.

Revision 5:
* Based on R.4a
  - reformatted and updated

* Eliminates climb milling cuts

* Adds rabbet for reduction of tongue length by 50mil.

* Use drawing newKey.5
  - The newKey.5 drawing adds guidepoint for tongue length trim.

{% comment %}
* Use drawing newKey.4
  - The newKey.4 drawing adds guidepoint for 1/4em first-pass at tongue
  __as well as several other points to assist with determining mill tool positioning.__

  - The newKey.3/4 drawing does not account for retracting the shoulders per.se.
         Instead, it removes the shoulders altogether.
         This has implications regarding the tongue length.
         __In the figure below this is evidenced by the round transition 
         from the tongue to the anchor depicted on the lower side of the key.__

{% include figure.html
           img-dir=image-dir
           img-file='newKey.4.datum.png'
           alt='Drawing of guide key 7 with reference points'
           caption='New Guide Key 7, rev 4 showing reference datum points for milling.'
%}
{% endcomment %}


<br>
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
hd | 4" x 10" Mill Tooling Plate | hold-down  
3/8em | End Mill Holder | 3/8" end mill
1/4em | End Mill Holder | 1/4" end mill
1/8em | End Mill Holder | 1/8" end mill
1/8sd | 1/8" collet | 1/8" short drill
1/8cd | 1/4" collet | 1/8" center drill
1/4cs | 1/4" collet | 1/4" countersink (1-flute 60$^{\circ}$)
5/16cs | 1/4" collet | 5/16" countersink (6-flute 60$^{\circ}$)
caliper | hand | digital caliper

## Procedure:

<br>
```
    In the following steps
      From X,Y,Z = 0,0,0 "Advance" moves into the workpiece
      Advance also means a clockwise turn of handwheel.

      The X,Y,Z = 0,0,0 position varies from step to step as the
      procedure evolves.  Often the nominal zero position of an end-mill
      places the X,Y,Z contact point for cutting to the left, behind,
      and above the left end of the workpiece.

      From a Z-down top view the tool rotates in a clockwise direction.

      From a Z-down top view, for standard milling, an end-mill cutter
      should follow a counter-clockwise path around the periphery of
      the workpiece.  Climb milling follows a clockwise path.  As a
      novice these instructions seek to avoid climb milling operations.
```
<br>
`In the following steps:`  
_`SC:`_`Standard Cut`  
_`CC:`_`Climb Cut`  
_`NCC:`_`No Climb Cut, No cut made despite climb direction motion`

<br>
1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, offset by one hole.
    * Tram adjust block parallel to X axis

    <br>
2. hd: Mount workpiece  

    * Workpiece: 0.25" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left (operator pov)
    * Add hold-downs using 1/4" rear support block (do not use step-blocks) 

    <br>
3. 3/8em: Square off end of workpiece

    Rigid 3/8em required to achieve suitable results.
    *  Retract Z and change tool.
    *  Gross center X Y at exposed end of workpiece
    *  Advance Z to touch
    *  Set Z=0
    *  Retract Z to -15mil from 0
    *  Visually locate nominal contact for X and Y and set X=0 and Y=0
    *  Retract X and Y to -200mil, -200mil from 0,0 position  
    (adjacent to left rear corner of workpiece)
    *  Advance Z to 200mil from -15mil
    *  Turn on mill
    *  Repeat to goal of squared workpiece end
       - Advance X for $\approx$20mil depth of cut
       - Advance Y to 450mil from -200mil (_SC_)
       - Retract Y to -200mil from 450mil (_NCC_)
    *  Turn off mill

    <br>
    ```
    To avoid Y backlash, in the following steps:
      Y will ONLY be advanced.
      X will return to -15mil after each cut.

      Objective is pre-cut with 1/4em to reduce subsequent 1/8em
      side cut depths to less than 10mil so as to avoid tool deviation
      due to side forces.
    ```

    <br>
4. 1/4em: Gross Cut first side of tongue (10mil oversize)

    * Retract Z and change tool.
    * Using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
      - X=0 is squared left workpiece end
      - Y=0 is rear workpiece surface, facing away from operator
      - Z=0 is upper surface
    * Retract Z to -15mil
    * Retract X to -15mil
    * Retract Y to -15mil
    * Advance Z to 150mil
    * Advance Y to 0mil
    * Turn on mill
    * Repeat to goal of Y=40mil:
      -  Advance X to 235mil from -15mil (_NCC_)
      -  Advance Y incrementally, by 5mil each, towards goal Y=40mil
      -  Retract X to -15mil from 235mil (_SC_)
    * Turn off mill
    * Leave Y at 40mil
    * Leave X at -15mil
    * Retract Z to -15mil from 150mil

    <br>
5. 1/4em: Gross cut second side of tongue (10mil oversize)
    * Retract X to -15mil
    * Retract Z to -15mil
    * Advance Y from 40mil to 460mil (10mil beyond final tongue edge)
    * Turn on mill
    * Repeat to goal of Z=150mil:
      -  Advance Z incrementally, 15mil per, towards goal Z=150mil
      -  Advance X to 235mil from -15mil (_SC_)
      -  Retract X to -15mil from 235mil (_NCC_)
    * Turn off mill
    * Leave Y at 460mil
    * Retract Z to -15mil
    * Retract X to -15mil

    * Deburr:
      -  Freecut: Advance Z to -1mil. X and Y as needed to deburr top edges
      -  Measure: tongue should be 190mil
      -  Measured: <ins>..........</ins> mil
      -  Appearance: <ins>...</ins>

    <br>
    ```
    In the following steps, that establish penultimate tongue width and  
    center the drill the screw hole, to avoid Y backlash:
      Y will ONLY be advanced (+ direction)
      X will retract to -15mil before next advance
      Penultimate tongue goal: 150 + 5 + 5 = 160mil
      Finished tongue goal: 155mil
      Polished tongue goal: 150mil (post milling to fit actual piston groove)
    ```

    <br>
6.  1/8em: Penultimate cut first side of tongue
    * Retract Z and change tool
    * Using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
      - Y=0 is contact surface away from operator
      - X=0 is squared bar end contact
      - Z=0 is upper surface contact
    * Retract X to -15mil, Y to -15mil, Z to -15mil.
    * Advance Z to 150mil from -15mil
    * Advance Y to 30mil from -15mil
    * Turn on mill
    * Repeat to goal Y = 45mil: (leaves 5mil excess of finished on side 1)
      -  Advance X to 213mil from -15mil (_NCC_)
      -  Advance Y incrementally, in 5mil increments, towards goal Y=45mil
      -  Retract X to -15mil from 213mil (_SC_)  
    * Retract Z to -15mil from 150mil
    * Turn off mill
    * Y is at 45mil
    * X is at -15mil

    <br>
7. 1/8cd: Locate screw hole and make divot
    * Retract Z and change tool
    * Advance Y from 45mil to 187.5mil
    * Advance X from -15mil to 432.5mil
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil from 0
    * Turn on mill
    * Advance Z to 20mil cutting hole center location divot
    * Retract Z to -15mil
    * Turn off mill

    <br>
8. 1/8sd: Drill screw hole
    * Retract Z and change tool
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil
    * Add cutting oil
    * Turn on mill
    * Drill 200mil hole by advancing Z to 200mil, adding oil as needed
    * Retract Z to -15mil
    * Turn off mill

    <br>
9.  1/4cs (1-flute 60$^{\circ}$): Countersink the screw hole  
    __This step is for the HIF6 1/8-40 BSW imperial screw.__
    * The top diameter of the chamfer must exceed 184mil
      to accomodate the BSW screw.  
      (as measured)

    <br>
    __/This step is the result of experimental procedure to 
    establish the countersink for the screw.
    See [Countersink experiment 7.5]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/machining/countersink.7.5.html" }})
    for details.
    /__

    For $S$=diameter of screw hole, $D$=diameter of cs, $H$=depth of cs, $\theta$=angle of countersink:  

    <p style="text-align: center;">
      $H = \frac{D-S}{2 tan(\frac{\theta}{2})}$
    </p>

    <p style="text-align: center;">
      $D = S + {2 H tan(\frac{\theta}{2})}$
    </p>

    For HIF6: $S$=125mil, $D$=185mil, $\theta$=60$^{\circ}$:  

    <p style="text-align: center;">
      $H = \frac{185-125}{2 tan(\frac{60}{2})} \approx 52mil$
    </p>

    As a result of the
    [experiment]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/machining/countersink.7.5.html" }}),
    while 52mil is technically the correct result,
    based on the original guide key,
    it was found that 60mil is better suited to the actual screw.

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole.
    * Advance Z to ohmmeter contact  
      _The tip of cs will be inside the screw hole.  
      The contact will be at the rim of the screw hole.  
      It may help to manually jog tool rotation as Z is advanced.  
      Try to avoid cutting the rim of the screw hole._
    * Set Z=0
    * Retract Z to -15mil from 0
    * Turn on mill
    * Advance Z to 60mil from -15mil 
    * Retract Z to -15mil from 0
    * Turn off mill
    * Measure: large diameter of cs should be $\approx$ 194mil
      + Diameter Measured: <ins>..........</ins> mil

    <br>
10. 1/8em: Penultimate cut second side of tongue  
    Goal: 160mil penultimate tongue width
    * Retract Z and change tool
    * Advance X to 150mil from -15mil
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil
    * Retract X to -15mil from 150mil
    * Advance Y to 330mil from 187.5mil (leaves 5mil excess of finished on side 2)
    * Turn on mill
    * Repeat to goal Z=150mil:
      -  Advance Z incrementally, 15mil per, towards goal Z=150mil
      -  Advance X to 213mil from -15mil (_SC_)
      -  Retract X to -15mil from 213mil (_NCC_)
    * Turn off mill
    * Retract X to -15mil
    * Retract Z to -100mil

    <br>
11. Caliper: Verify penultimate tongue is 160mil wide  
    Expected penultimate tongue width is 160mil, desired finished is 155mil  
    * Measure: tongue should be 160mil
      + Penultimate Measured: <ins>..........</ins> mil
      + Appearance: <ins>...</ins>
      + Compute __delT__ = PenultimateMeasured - 155 : <ins>..........</ins> mil
      + Compute __delT/2__ : <ins>..........</ins> mil (Round down to nearest mil)

    <br>
    ```
    The penultimate tongue width and centered screw hole is now established.  
    Goal is to reduce total tongue width by delT to finish target of 155mil.  
    It is assumed that the Y leadscrew is the ultimate reference and that
    the tongue centerline is to remain coincident with the screw hole.

    To avoid Y backlash:
      Y will be retracted prior to advancing 
      X will retract to -15mil before next advance
      Finished tongue goal: 155mil
    ```
    <br>
12. 1/8em: Finish cut second side of tongue  
    Y is at 330mil from previous step
    * Compute __Y2__ = 330 - delT/2: <ins>..........</ins> mil
    * Compute __Y2retract__ = Y2 - 15mil: <ins>..........</ins> mil
    * Retract Y to __Y2retract__
    * Advance Z to 150mil from -100mil
    * Advance X to 254mil from -15mil 
    * Turn on mill
    * Advance Y to __Y2__ (eliminates backlash)
    * Retract X to -15mil from 254mil (_SC_)
    * Turn off mill
    * Retract Z to -15mil from 150mil

    <br>
13. 1/8em: Finish cut first side of tongue  
    Y is at _Y2_ from previous step
    * Compute __Y1__ = 45 + delT/2: <ins>..........</ins> mil
    * Retract Y to 30mil
    * Advance Y to __Y1__ (eliminates backlash)
    * Advance Z to 150mil from -15mil
    * Turn on mill
    * Advance X to 254mil from -15mil (_SC_)
    * Retract X to -15mil from 254mil (_NCC_)
    * Turn off mill
    * Retract Y to -15mil from __Y1__
    * Retract Z to -100mil from 150mil

    <br>
14. Caliper: Verify final tongue is 155mil wide  
    * Measure: tongue width should be 155mil
      - Final Measured: <ins>..........</ins> mil
      - Appearance: <ins>...</ins>
      - Compute __delF__ = FinalMeasured - 155 : <ins>..........</ins> mil

    <br>
15. 1/8em: Top side dado for cut off.  
    > Note: I can find no reference to confirm or deny that cutting a dado
    > in this manner is an appropriate use of an end mill.  

    Cut 20mil deep dado on anchor heel:
    * Retract Y to -15mil
    * Advance X to 695mil from -15mil 
    * Advance Z to 10mil from -100mil
    * Turn on mill
    * Advance Y to 400mil from -15mil (_SC_)
    * Retract Y to -15mil from 400mil (_NCC_)
    * Advance Z to 20mil
    * Advance Y to 400mil from -15mil (_SC_)
    * Retract Y to -15mil from 400mil (_NCC_)
    * Turn off mill
    * Retract Z to -15mil from 20mil
    * Retract X to -15mil from 695mil

    <br>
16. Gross cut rabbet to reduce tongue length  
    > Tongue length prior to this cut: 150mil  
    > Nominal length in-situ (unconfirmed): 80mil  
    > Length reduction this cut: 50mil  
    > Length after this cut: 100mil  
    > Oversize beyond nominal of 80mil: 20mil
    >
    > Fitting and measuring will yield a better
    > idea of what the nominal tongue length should be.  
    > It may be better to make a fixture solely for trimming
    > the tongue length, and perhaps the width polishing...
    >
    > This step reduces the tongue length from 150mil to 100mil.  
    > The nominal tongue length is 80mil, subject to fitting.  

    Cut rabbet for gross tongue end:
    * Advance X to 50mil from -15mil 
    * Turn on mill
    * Repeat to goal Z=120mil:
      - Advance Z incrementally, 15mil per, towards goal Z=150mil
      - Advance Y to 400mil from -15mil (_SC_)
      - Retract Y to -15mil from 400mil (_NCC_)
    * Turn off mill
    * Retract Z to -15mil from 120mil
    * Retract X to -15mil from 50mil

    <br>
17. 3/8em: Fly cut top surface to deburr
    * Retract Z and change tool.
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil from 0
    * Freecut: Advance Z to -1mil. X and Y as needed to deburr top
    * Clean up as necessary.  
 
    <br>
18. Flip the workpiece over to work on bottom of guideKey.
    * Dismount workpiece
    * Rotate 180deg so that guide key bottom surface is facing upwards.
    * Remount facing left (in the same direction as before.)

    <br>
19. 3/8em: Rabbet part end to expose tongue tip

    Goal here is to expose tongue tip for X alignment.  
    The rabbet cut in this step will be removed on the subsequent fly cut

    * Advance Z and locate Z$\approx$0
    * Retract Z to -50mil
    * Gross align Y at part center, X above uncut surface 
    * Advance Z to ohmmeter touch top surface.
    * Set Z=0
    * Retract Z to -15mil from 0
    * Gross align X for tool to just overhang-intersect tongue tip
    * Gross align Y for tool off surface on far side of part
    * Set Y=0
    * Retract Y to -15mil
    * Turn on mill
      - Incrementally advance Z, by 15mil, to goal of Z$\approx$60mil  
        Repeat until tongue tip is just exposed
      - Advance Y to 650mil from -15mil (_SC_)
      - Retract Y to -15mil from 650mil (_NCC_)
    * Turn off mill
    * Retract Z to -15mil  
    * Retract Y to -15mil (if at 650mil)  

    <br>
20. 3/8em: Fly cut to reduce remaining thickness to 100mil  

    Goal here is to remove a total of 150mil of material
    for a 100mil final thickness of key.  
    Also leaves room for 1/8" anchor cutoff dado

    * Advance Y to 500mil (end mill Y-centered over part)  
    * Retract X such that tool edge is perhaps 50mil gap to tongue tip
    * Advance X such that tool edge is perhaps 10mil gap to tongue tip
    * Set X=0
    * Retract X to -15mil from 0
    * Z is at -15mil from previous step
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of 150mil
      - Full Sweep X: (advance to X=650mil, retract to X=-15mil)  
      __Leave at X=650mil on final sweep to save time__  
    * Turn off mill
    * Retract Z to -15mil from 150mil 
    * Retract Y to -15mil from 500mil 

    <br>
21. 3/8em: Square off semi-circular step at the advanced X end of part.  
    Step needs to be squared off so that remaining bar material is square.

    * Advance X to 665mil from 650mil  
    * Turn on mill
      - Incrementally advance Z, by 15mil, to goal of 145mil
      - Full Sweep Y: advance to Y=700mil (_SC_), retract to Y=-15mil(_NCC_)  
      Note: this cut is on the bar, not the workpiece
    * Turn off mill
    * Retract Z to -15mil from 145mil  
    * Retract X to -15mil from 665mil  
    * Retract Y to -15mil

    <br>
22. 1/8em: Dado between anchor and tongue  

    Goal is 20mil deep dado

    * Retract Z and change tool.
    * Gross center Y X
    * Advance Z to ohmmeter touch
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract X for tool beyond tongue tip
    * Advance Z to 50mil from 0
    * Advance X to ohmmeter touch tongue tip at em cutting edge
    * Set X=0
    * Advance to X=350mil
    * Gross align Y beyond part with ~15mil clearance
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -15mil from 50mil
    * Retract X to 190mil from 350mil
    * Advance X to 205mil from 190mil (remove backlash)
    * Turn on mill
    * Advance Z to 10mil from -15mil
    * Advance Y to 440mil cutting shallow dado
    * Advance Z to 20mil from 10mil
    * Retract Y to -15mil completing 20mil dado
    * Turn off mill
    * Retract Z to -15mil from 20mil

    <br>
23. 5/16cs: chamfer Dado at tongue edge

    Goal is 18mil chamfer of 20mil dado edge

    __Does it matter which angle for the 5/16cs?__

    * Retract Z and change tool.
    * Retract X to 125mil from 205mil
    * Advance X to 142mil from 125mil (remove backlash)
    * Advance Y to 100mil from -15mil  
    <br>
    __==> non-existent tip of cs is now over dado edge, 0.5mil offset towards tongue__

    * Visually confirm position and correct if needed
    * Advance Z to ohmmeter contact (tip of cs will overhang edge)
    * Set Z=0
    * Retract Z to -20mil
    * Advance Z to -5mil
    * Advance X such that cutting edge of cs visually ~20mil beyond dado edge.  
    * Retract X such that cutting edge of cs visually ~5mil beyond dado edge.  
      The blunt tip of the cs will be entirely above the dado.
    * Advance Z to 5mil from -5mil
    * Turn on mill
    * __Watch carefully__ and retract X until cs just barely starts cutting edge.
    * Turn off mill
    * Retract Z to -12mil
    * Advance Y to 400mil from 100mil
    * Turn on mill  
      Goal is to create Z=18mil chamfer: 
      - Incrementally advance Z, by 10mil, to goal of 18mil
      - Full Sweep Y: retract to Y=-15mil(_SC_), advance to Y=400mil (_NCC_),  
    * Turn off mill
    * Retract Z to -15mil
    * Retract X to -15mil from X$\approx$142mil
    * Retract Y to -15mil from 400mil

    <br>
24. 1/8em: Deep dado to meet top-side dado resulting in cutoff at anchor end

    Goal is new dado to meet opposing 20mil dado, cutting off guideKey

    * Retract Z and change tool.
    * Advance Y to 100mil from -15mil
    * Advance X to 645mil from -15mil
    * Advance Z to ohmmeter touch
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract Y to -15mil from 100mil
    * Clamp two-hole wood block using hex bolts across key as a hold down
    for final cutoff.
    * Turn on mill  
      Goal is to meet 20mil opposing dado resulting in cut off at Z=130mil.
      - Incrementally advance Z, by 10mil, to goal of 130mil
      - Half Sweep Y: (retract to Y=-15mil or advance to Y=400mil)
    * Turn off mill
    * Retract Z to -15mil

    <br>
25. __Finishing and trimming tongue to length is left as a future exercise.__

<br>

---

<br>

### Final dimensions, mils:

| __FEATURE__ | __TARGET, mil__ | __ACTUAL__ |
| ----------- |:----------:| ----------:|
tongue width | 150 | ..... 
tip to heel | 520 | .....
heel to hole edge | 137.5 | .....
tip to hole edge | 257.5 | .....
hole diameter | 125 | .....
side 1 to hole | 62.5 | .....
side 2 to hole | 62.5 | .....
side 1 to side 2 | 250 | .....
key thickness | 100 | .....

### Notes:

{% comment %}
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[markdown syntax](https://learn-markdown.github.io/assets/markdown-cheatsheet.pdf)
{% endcomment %}
