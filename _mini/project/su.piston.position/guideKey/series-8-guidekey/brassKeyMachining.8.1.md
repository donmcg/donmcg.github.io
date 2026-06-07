---
layout: default
title: Proposal Rev.1 - Series 8 Guide Key Machining 
tip: machining brassKey.10, rev 1
date:   2026-06-06 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.8 ] # applies to chapter level
  blog: project/su.piston.position/guideKey/series-8-guidekey
---

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/thumbs/
{% endcapture %}
{% comment %}
  use thumbs for actual printing...  saves a lot of paper!
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/thumbs/
{% endcomment %}

Last update {{ page.date | date: "%d %b %Y" }}.

Series 8 Brass Key Machining Proposal Revision 1:
* Proposal 8.1 based on
    [Rev.7 Guide Key 7 Machining Proposal]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-7-guidekey/newKeyMachining.7.7.html" }})

* Produces fifth physical newKey, aka brassKey10

* Use drawing brassKey.10.4
{% include figure.html
           img-dir=image-dir
           img-file='pocket19-comp.png'
           alt='series 8 brass key finished'
           caption='Series 8 Guide Key'
%}

<br>
* Primary changes from series 7 
  - 5/16" starting material
  - Tongue with fillet extends above upper surface of key
  - Sensor bonded to back side of tongue with adhesive

<br>
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
mic | Handheld | Micrometer Gauge
di | diBase | Dial Indicator Gauge
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
hd | 4" x 10" Mill Tooling Plate | hold-down  
vise | 4" x 10" Mill Tooling Plate | milling vise, Sherline 3551
ef | End Mill Holder | edge finder, Starrett 827A
3/8em | End Mill Holder | 3/8" end mill
1/4em | End Mill Holder | 1/4" end mill
1/8em | 1/8" collet | 1/8" end mill
1/8rem | 1/8" collet | 1/8" radius 0.01" end mill
050em | End Mill Holder | 0.05" end mill
7/64sd | chuck | 7/64" short drill
1/8sd | 1/8" collet | 1/8" short drill
1/8cd | 1/4" collet | 1/8" center drill
1/4cs | 1/4" collet | 1/4" countersink (1-flute 60$^{\circ}$)
5/16cs | 1/4" collet | 5/16" countersink (6-flute 60$^{\circ}$)
caliper | hand | digital caliper

## Procedure:

```
In the following steps:

From X,Y,Z = 0,0,0 "Advance" moves into the workpiece
Advance also means a clockwise turn of handwheel.

The X,Y,Z = 0,0,0 position varies from step to step as the
procedure evolves.  Often the nominal zero position of an end-mill
places the X,Y,Z contact point for cutting to the left, behind,
and above the left end of the workpiece. The word 'cut' is 
used to emphasize that the 0 positon is set with respect to 
where the cutting edge of the tool touches the surface.

From a Z-down top view the tool rotates in a clockwise direction.

From a Z-down top view, for standard milling, an end-mill cutter
should follow a counter-clockwise path around the periphery of
the workpiece.  Climb milling follows a clockwise path.  As a
novice these instructions seek to avoid climb milling operations.

Hence an outside cut around the part would start on sideA, continue
around endB, and finish along sideC.
```

In the following steps:  
_`SC:`_ Standard Cut  
_`CC:`_ Climb Cut   
_`NCC:`_ No Climb Cut, No cut made despite climb direction motion

```
Definitions:
  * topZ is the upper surface of the workpiece.
  * sideA is the surface of the workpiece bar opposite the operator.
  * endB is the exposed end of the workpiece that faces to the operator's left.
  * sideC is the surface of the workpiece bar closest to the operator.  
    (The sideC surface is against the mounting block.)
  * botZ is the bottom surface of the workpiece.
    (The botZ surface is initially against the table.)
  * tongueA is the side of the tongue offset from sideA
  * tongueB is the tip of the tongue offset from endB
  * tongueC is the side of the tongue offset from sideC
  * obsolete: tongueF is the bottom side of the tongue opposing topZ
  * topT is the upper surface of the tongue
  * botT is the bottom surface of the tongue
  * topK is the upper surface of the key anchor
  * botK is the bottom surface of the key anchor
```

<br>
1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Mount block in extreme left position.
    * Tram align block parallel to X axis.

    <br>
2. hd: Mount workpiece  

    * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left (operator pov)
    * Add hold-downs using >5/16" rear support block (do not use step-blocks) 
      - sideC is facing up.
      - topZ is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}pocket1-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    <br>
2. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  
   This step leaves an $\approx$ 1/16" lip, at botZ, beyond the endB surface
   depending on the initial quality of the workpiece end.

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at sideC using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond topZ
    * Advance X to 250mil from -15mil
    * Set Y=0 at topZ using ohmmeter
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Retract X to -15mil from 250mil
    * Advance Z to 260mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$10mil total depth of cut and visually smooth.
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}pocket2-comp.png)
    Squared endB with remaining lip

   <br>
4.  3/8em: Reduce to 1/4" width of anchor to establish sideA

    > Note: this first section yielded poor results.  Why?
    * Retract Z.
    * Rotate workpiece 180$^{\circ}$, endB lip is uppermost.
      - sideA is facing up.
      - endB is facing to left.
      - botZ is facing away from operator
     Gross center Y, tool overlaps both sides of workpiece
    * Adjust X to just beyond lip at endB of workpiece, lower Z as needed.
    * Set X=0 (gross)
    * Retract X to -50mil from 0
    * Advance Z to approach surface of tooling plate
    * Set Z=0 at tooling plate using ohmmeter
    * Retract Z to -350mil from 0: tool is $\approx$37.5mil above top of workpiece
    * Advance Z to -320mil from -350mil
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of -250mil
      - Full Sweep X: (advance to X=750mil, retract to X=-50mil)
        * 15 rotations of X knob from X=0 to X=750
    * Turn off mill
    * X is at -50mil
    * Clean area then check height by comparing against 1/4" bar stock.
    * Advance Z to -200mil from -250mil
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -320mil from -200mil
    * Retract Y just beyond botZ
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Advance X to 750mil from 0 (15 rotations)
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of -250mil
      - Full Sweep Y: (advance to Y=600mil, retract to Y=-50mil)  
        * 13 rotations of X knob from Y=0 to Y=600
    * Turn off mill
    * Retract Z to -350mil from -250mil
    * Remove workpiece from table
    >
    * Measure: sideA to sideC; should be 250mil +5 -0
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>
    >

    Note: trial procedure follows
    * Retract Z
    * Remove workpiece and deburr edge at endB / sideB
      - it must be able to lay flat on table
    * Rotate workpiece 180$^{\circ}$, endB lip is uppermost.
      - sideA is facing up.
      - endB is facing to left.
      - botZ is facing away from operator
     Gross center Y, tool overlaps both sides of workpiece
    * Adjust X to just beyond lip at endB of workpiece, lower Z as needed.
    * Set X=0 (gross)
    * Advance X to 400mil from 0
    * Set Z=0 at sideA using ohmmeter
    * Retract Z to -15mil from 0
    * Retract X to -50mil from 0
    * Advance Z to 10mil from -15mil
    * Turn on mill
      - Full Sweep X: (advance to X=750mil, retract to X=-50mil) 
        + 15 rotations of X knob from X=0 to X=750
    * Turn off mill

    * $\boldsymbol{\xi}$ &nbsp; &nbsp;  X is at -50mil
    * Retract Z
    * Clean area then measure $\eta$, height from table to fresh cut using dial indicator
      - Measured: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;    ...</ins> mil
      - Appearance: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;   ...</ins>
      - Evaluate planarity; is it level across entire cut?
    * Compute new Z goal, $\zeta$, where $\zeta$ = **260** - $\eta$ mil
    * Advance X to 400mil from -50mil
    * Set Z=0 at sideA using ohmmeter
    * Retract Z to -15mil from 0
    * Retract X to -50mil from 0
    * Advance Z to 10mil from -15mil
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of $\zeta$ mil
      - Full Sweep X: (advance to X=750mil, retract to X=-50mil)
        * 16 rotations of X knob from X=-50 to X=750
      - Brush tool cutting edge and surrounding area to clear debris
      - Continue from $\boldsymbol{\xi}$ if desired
    * Turn off mill

    * Repeat from $\boldsymbol{\xi}$ with modifications:
      - This is the final setting of sideA
      - Compute final Z goal, $\zeta$, where $\zeta$ = **250** - $\eta$ mil
      - Perhaps use 5mil increments, or less

    <br>
    * Z is at final $\zeta$ with sideA at 250mil above table
    * X is at -50mil
    * Set Z=0
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -100mil from 50mil
    * Retract Y just beyond botZ
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Advance X to 750mil from -15mil (15$^+$ rotations)
    * Advance Z to -70mil from -100mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 0mil
      - Full Sweep Y: (advance to Y=600mil, retract to Y=-50mil)  
        * 14 rotations of X knob from Y=-50 to Y=600
    * Turn off mill
    * Retract Z
    * Remove workpiece from table
    
    * Measure: sideA to sideC; should be 250mil +5 -0
      - Measured: <ins>... &nbsp; &nbsp; &nbsp; &nbsp;  ...</ins> mil
      - Appearance: <ins>...    ...</ins>

    <br>

    ![]({{image-dir}}pocket3-comp.png)
    SideA is facing upwards.

    <br>
5.  ef: Locate hole for adhesive arch

    Much of the area around this hole will be cut away in subsequent steps.


    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing downwards.
      - sideC is facing upwards.
      - botZ is facing operator.
      - endB is facing to left.
    * Gross adjust Y for tool centered on sideC, X for tool beyond endB
    * Gross set Z=0 at sideC
    * Advance Z to 150mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Advance Y beyond botZ
    * Advance X to 195mil from -15mil
    * Turn on mill
    * Jog Y so as to retract Y to indicate botZ edge via ef
    * Turn off mill
    * Set Y=0
    * Advance Y to +15mil from 0
    * Retract Z to -50mil from 150mil
    * Retract Y to -210mil from +15mil
    * X,Y are now centered on screw hole

    <br>
6. 1/8cd: Cut guide divot for drill in topZ
    * Retract Z and change tool
    * Recenter X,Y at (195,-210) to remove backlash
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 20mil cutting divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
7. 7/64sd: Drill hole to form arch behind tongue  
    * Retract Z and change tool
    * Recenter X,Y at (195,-210) to remove backlash
    * Advance Z and locate Z$\approx$0  
      Use ohmmeter contact with divot as Z=0 
      Drill bit point is inside divot, outer corner at sideC 
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill pocket by advancing Z to 250mil, 50mil at a time,
    adding oil each thrust
    * Retract Z to -15mil from 250mil
    * Turn off mill

    ![]({{image-dir}}pocket4-comp.png)
    Hole for arch. SideA facing down, sideC facing up.

    <br>
8. 1/4em: Gross Cut tongueA (10mil oversize)  
   Gross cut of tongueA and tongueC yields gross tongue width 140 + 10 + 10 = 160mil

    * Retract Z and change tool.
    * Rotate workpiece 90$^{\circ}$ such that sideA is facing away from operator
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Using ohmmeter establish Z=0 @topZ, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed endB of workpiece
      - Set Z=0 at topZ using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 170mil from -15mil
      - Set Y=0 cut at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * X is at 170mil
    * Advance Z to 300mil from 50mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=45mil:
      - Advance Y in 5mil steps to goal of 45mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=170mil(_NCC_)  
    * Turn off mill
    * Retract Y to -15mil from 45mil
    * Retract X to -15mil from 170mil
    * Retract Z to -15mil from 300mil

    <br>
9. 1/4em: Gross Cut tongueC (10mil oversize)  
   Gross cut of tongueA and tongueC yield gross tongue width 140 + 10 + 10 = 160mil

    * Advance Y to 550mil from -15mil (cut beyond sideC)
    * Advance X to 170mil from -15mil
    * Advance Z to 50mil from -15mil
    * Set Y=0 cut at sideC using ohmmeter
    * Advance Y to +15mil from 0
    * Advance Z to 300mil from 50mil
    * Retract X to -15mil from 170mil
    * Retract Y to +5mil from +15mil (remove backlash)
    * Turn on mill
    * Repeat to goal of Y=-45mil:
      - Retract Y in 5mil steps to goal of -45mil
      - Full Sweep X: advance to X=170mil (_SC_), retract to X=-15mil(_NCC_)  
    * Turn off mill
    * X is at -15mil
    * Advance Y to +15mil from -45mil
    * Retract Z to -15mil from 300mil
    * Deburr:
      - Freecut: Advance Z to -1mil. X and Y as needed to deburr top edges.

    ![]({{image-dir}}pocket6-comp.png)
    Gross tongueA and tongueC
    <br>
    * Measure: tongueA to tongueC (at tip) should be 160mil
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>

    <br>
10. 1/4em: Establish botT, the lower surface of the tongue

    * Rotate workpiece 180$^{\circ}$
      - sideA is facing operator.
      - sideC is facing away from operator.
      - botZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Set Z=0 at botZ using ohmmeter
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Advance X to 60mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil
    * Y is at -50mil
    * Advance X to 175mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80$^-$mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil

    ![]({{image-dir}}pocket7-comp.png)
    Lower surface of tongue

    <br>
11. 1/8em: Establish cantilever at lower end of tongue

    * Retract Z and change tool
    * Gross center X,Y
    * Set Z=0 at botZ using ohmmeter
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 100mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to 50mil from100mil 
    * Advance Z to 70mil from50mil 
    * Advance X to 165mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 110mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 110mil
    ```
    Note that the ideal of setting the cantilever surface tangent to the hole
    assumes the 1/8em tool is actually 125mil diameter.  In practice
    it may be less than that. This will leave a small step at the hole.
    This step, which indicates that the cantilever is slightly thick,
    is desirable and should be left as is.
    ```

    ![]({{image-dir}}pocket8-comp.png)
    Cantilever at lower end of tongue

    <br>
12. 3/8em: Establish topT, the upper surface of the tongue

    * Rotate workpiece 180$^{\circ}$
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Set Z=0 at topZ using ohmmeter
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideA
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Advance X to 150mil from -15mil
    * Advance Z to +2.5mil from -15mil
    * Turn on mill
    * Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 2.5mil
    * Y is at -50mil
    * X is at 150mil

    ![]({{image-dir}}pocket9-comp.png)
    Upper surface of tongue

    <br>
13. 3/8em: Establish topK, the upper surface of the key anchor

    * X,Y,Z is 150,-50,-15 mil
    * Advance X to 475mil from 150mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil
    * Advance X to 600mil from 475mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil
    * Advance X to 750mil from 600mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil

    ![]({{image-dir}}pocket10-comp.png)
    Upper surface of anchor

    <br>
14. 1/8rem: Fillet on rear of tongue

    ```
    1/8rem bit has 10thou radius.
    ```

    * Retract Z and change tool
    * Gross center X,Y
    * Set Z=0 at topZ using ohmmeter
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideA
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Advance X to 225mil from -15mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80$^-$mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 80mil

    ![]({{image-dir}}fillet0-comp.png)
    Fillet on rear of tongue

    <br>
15. ef: Locate screw hole center 

    * Retract Z and change tool
    * Gross adjust X,Y for tool centered on tongue beyond endB
    * Gross set Z=0 at topT
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB position via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 50mil
    * Retract Y beyond sideA
    * Advance X to 100 + 285 = 385mil from -15mil
    * Gross center Y
    * Gross set Z=0 at topK
    * Retract Z to -15mil 0
    * Retract Y beyond sideA
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog Y so as to advance Y to indicate sideA position via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 100 + 125 = 225mil from -15mil
    * X,Y are now centered on screw hole

    <br>
16. 1/8cd: Cut guide divot for drill in topZ
    * Retract Z and change tool
    * Advance Z to topK using ohmmeter
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract X and Y then advance back to 385,225 (remove backlash)
    * Add cutting oil
    * Turn on mill
    * Advance Z to 20mil cutting divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
17. 1/8sd: Drill pocket for screw hole
    * Retract Z and change tool
    * Advance Z to topK divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract X and Y then advance back to 385,225 (remove backlash)
    * Add cutting oil
    * Turn on mill
    * Drill 100mil pocket by advancing Z to 100mil, 50mil at a time, adding oil each thrust
    * Retract Z to -15mil from 100mil
    * Turn off mill

    ![]({{image-dir}}pocket12-comp.png)
    Pocket for screw hole

    <br>
18. 1/4cs (1-flute 82$^{\circ}$): Countersink the screw hole  
    __These dimensions are for the standard HIF44 screw and the substitue #4-40 screw.__
    * The top diameter of the chamfer must exceed ???mil
      to accomodate the #4-40 screw.  
      (as measured)

    <br>
    __/This step is the result of experimental procedure to 
    establish the countersink for the screw.
    See [Countersink experiment 7.5]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-7-guidekey/countersink.7.5.html" }})
    for details.
    /__

    For $S$=diameter of screw hole, $D$=diameter of cs, $H$=depth of cs, $\theta$=angle of countersink:  

    <p style="text-align: center;">
      $H = \frac{D-S}{2 tan(\frac{\theta}{2})}$
    </p>

    <p style="text-align: center;">
      $D = S + {2 H tan(\frac{\theta}{2})}$
    </p>

    For #4-40: $S$=125mil, $D$=250mil, $\theta$=82$^{\circ}$:  

    <p style="text-align: center;">
      $H = \frac{250-125}{2 tan(\frac{82}{2})} \approx 72mil$
    </p>

    In practice the 72mil depth should be considered the maximum limit.
    A #4-40 x 1/4" screw will drop into the hole and serve as a 
    progress indicator.  The ideal is the top of the screw is flush with topZ.

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Retract X and Y then advance back to 385,225 (remove backlash)
    * Advance Z to ohmmeter contact at topK 
      _The tip of cs will be inside the screw hole.  
      The contact will be at the rim of the screw hole.  
      It may help to manually jog tool rotation as Z is advanced.  
      Try to avoid cutting the rim of the screw hole._
    * Set Z=0
    * Retract Z to -100mil from 0
    * Turn on mill
    * Repeat to goal of Z=72mil or flush screw:
      - Advance Z towards 72mil from -100mil 
      - Retract Z to -100mil 
      - Check depth progress with #4-40 x 1/4" screw
      - Apply some judgement
      - Leave Z at -100mil once depth is established  
    * Turn off mill

    ![]({{image-dir}}chamfer0-comp.png)
    Countersink for screw hole

    * Measure: large diameter of cs should be $\approx$250mil
      + Diameter Measured: <ins>...     ...</ins> mil

    <br>
19. 3/8em: Establish botK, the lower surface of the key anchor

    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing operator.
      - sideC is facing away from operator.
      - botZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Set Z=0 at botZ using ohmmeter
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 150mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideA
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 150mil
    * Advance X to 460mil from -15mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 160mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 160mil
    * Advance X to 600mil from 460mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 160mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 160mil

    ![]({{image-dir}}pocket13-comp.png)
    Bottom surface of anchor

    <br>
20. 1/8em: Final Cut tongueA
   Final cut of tongueA and tongueC yields tongue width 140mil
    ```
    For final width of 150mil use delta Y = 50 instead of 55mil
    ```

    * Retract Z and change tool.
    * Using ohmmeter establish Z=0 @topT, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed endB of workpiece
      - Set Z=0 at topT using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 200mil from -15mil
      - Set Y=0 cut at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * Retract X to 100mil from 200mil
    * Advance X to 148mil from 100mil
    * Advance Z to 300mil from 50mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=55mil:
      - Advance Y in 5mil steps to goal of 55mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=148mil(_NCC_)  
    * Turn off mill
    * Retract Y to -15mil from 55mil
    * Retract X to -15mil from 148mil
    * Retract Z to -15mil from 300mil

    <br>
21. 1/4em: Final Cut tongueC 
   Final cut of tongueA and tongueC yield tongue width 140mil

    * Advance Y to 550mil from -15mil (cut beyond sideC)
    * Advance X to 200mil from -15mil
    * Advance Z to 50mil from -15mil
    * Set Y=0 cut at sideC using ohmmeter
    * Advance Y to +15mil from 0
    * Advance Z to 300mil from 50mil
    * Retract X to -15mil from 200mil
    * Retract Y to +5mil from +15mil (remove backlash)
    * Turn on mill
    * Repeat to goal of Y=-55mil:
      - Retract Y in 5mil steps to goal of -55mil
      - Full Sweep X: advance to X=148mil (_SC_), retract to X=-15mil(_NCC_)  
    * Turn off mill
    * X is at -15mil
    * Advance Y to +15mil from -55mil
    * Retract Z to -15mil from 300mil

    ![]({{image-dir}}pocket15-comp.png)
    Final tongueA and tongueC

    <br>
    * Measure: tongueA to tongueC (at tip) should be 140mil
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>

    <br>
22. 050em: Adhesive overflow channel

    ```
    This step is intentionally delayed to this point to minimize the
    material removed by this small tool.
    ```
    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing operator.
      - sideC is facing away from operator.
      - botZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Adjust X to just beyond endB of workpiece
    * Advance Z to just above botT
    * Set Z=0 
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 200mil from -15mil
    * Gross center Y
    * Set Z=0 at botK using ohmmeter
    * Retract Z to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -50mil from -15mil
    * Advance X to 130mil from -15mil
    * Advance Z to -2mil from -50mil 
    * Turn on mill
      - Incrementally advance Z, in 2mil increments to goal of 10mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 10mil

    ![]({{image-dir}}pocket16-comp.png)
    Adhesive overflow channel

    <br>
23. 1/8em: Preliminary dado for key cut off.

    Goal is 20mil deep dado in botK surface

    * Retract Z and change tool.
    * Gross center Y over botK
    * Adjust X to just beyond endB of workpiece
    * Advance Z to just above botT
    * Set Z=0 
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 200mil from -15mil
    * Gross center Y over botK
    * Set Z=0 at botK using ohmmeter
    * Retract Z to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -50mil from -15mil
    * Advance X to 560mil from -15mil
    * Advance Z to -5mil from -50mil 
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of 20mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 20mil

    ![]({{image-dir}}pocket17-comp.png)
    Preliminary dado for cut off

    <br>
24. 1/8em: Penultimate dado for key cut off.

    Goal is 40mil deep dado in topK surface

    * Rotate workpiece 180$^{\circ}$
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Gross center Y over topK
    * Adjust X to just beyond endB of workpiece
    * Advance Z to just above topT
    * Set Z=0 
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 200mil from -15mil
    * Gross center Y over topK
    * Set Z=0 at topK using ohmmeter
    * Retract Z to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -50mil from -15mil
    * Advance X to 560mil from -15mil
    * Advance Z to -5mil from -50mil 
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of 40mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 40mil

    ![]({{image-dir}}pocket18-comp.png)
    Penultimate dado for cut off

    <br>
25. 1/8em: Ultimate dado for key cut off.

    Goal is 10mil deep dado in topK surface to separate guide key from workpiece

    * Advance Z to 40mil from -15mil 
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of $\approx$10mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil)  
    * Turn off mill
    * Retract Z to -15mil from 40mil

    ![]({{image-dir}}pocket19-comp.png)
    Ultimate dado for cut off: ta-da! brassKey is separated

<br>

---

<br>

### Final dimensions, mil

| __FEATURE__ | __TARGET, mil__ | __ACTUAL__ |
| ----------- |:----------:| ----------:|
tongue width | 140 | ...     ... 
tongue height | 230 | ...     ...
upper tongue thickness | 85 | ...     ...
lower tongue thickness | 40 | ...     ...
endB to heel | 435 | ...     ...
heel to hole edge | 87.5 | ...     ...
endB to hole edge | 222.5 | ...     ...
hole diameter | 125 | ...     ...
side 1 to hole | 62.5 | ...     ...
side 2 to hole | 62.5 | ...     ...
side 1 to side 2 | 250 | ...     ...
key thickness | 70 | ...     ...

### Notes:


{% comment %}
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[markdown syntax](https://learn-markdown.github.io/assets/markdown-cheatsheet.pdf)
{% endcomment %}

``` bash 
$ mkdir thumbs
$ cd thumbs
$ cp ../*.png .
$ magick mogrify -format png -thumbnail 200x200 *.png
-or-
$ mkdir thumbs
$ magick mogrify  -format gif -path thumbs -thumbnail 200x200 *.jpg
```

