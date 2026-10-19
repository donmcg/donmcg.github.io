---
layout: default
title: Proposal Rev.2 - Series 8 Guide Key Machining 
tip: machining brassKey.10, rev 2
date:   2026-10-17 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.8 ] # applies to chapter level
  blog: project/su.piston.position/guideKey/series-8-guidekey
---

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/thumbs.tmp/
{% endcapture %}
{% comment %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/
  use thumbs for actual printing...  saves a lot of paper!
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/series-8/thumbs.tmp/
{% endcomment %}

Last update {{ page.date | date: "%d %b %Y" }}.

Series 8 Brass Key Machining Proposal Revision 2:
* Proposal 8.2 based on
    [Rev.1 Guide Key 8 Machining Proposal]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-8-guidekey/brassKeyMachining.8.1.html" }})

* Produces sixth physical newKey, aka brassKey11
  - Updated based on notes taken when producing brassKey10

* Use drawing brassKey.10.4
{% include figure.html
           img-dir=image-dir
           img-file='guideKey-8-comp.png'
           alt='series 8 brass key finished'
           caption='Series 8 Guide Key'
%}

<br>
* Primary changes from series 7 
  - 5/16" starting material
  - Tongue with fillet extends above upper surface of key
  - Sensor bonded to back side of tongue with adhesive

<br>
{% comment %}
<div style="page-break-after: always;"></div>
{% endcomment %}
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
caliper | Handheld | Micrometer Gauge
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
Definitions (standard orientation):
  * N rot or N rotations means N turns of knob or N * 50mil
    - typically one rotation is from the 0 mark to 0 mark
  * topZ is the upper surface of the workpiece: the standard orientation.
  * endB is the exposed end of the workpiece that faces to the operator's left.
  * sideA is the surface of the workpiece bar opposite the operator.
  * sideC is the surface of the workpiece bar closest to the operator.  
    (The sideC surface is against the mounting block.)
  * botZ is the bottom surface of the workpiece.
    (The botZ surface is initially against the table.)
  * tongueA is the side of the tongue offset from sideA
  * tongueB is the tip of the tongue offset from endB
  * tongueC is the side of the tongue offset from sideC
  * topT is the upper surface of the tongue
  * botT is the bottom surface of the tongue
  * topK is the upper surface of the key anchor
  * botK is the bottom surface of the key anchor
```

   <br>
1. tram / 4hblk: Mount and tram block as straight edge for workpiece 

   * Mount block along front edge of tooling plate, exposing two rows of holes.
   * Mount block in extreme right position to leave room for the dial indicator
     to the left of the workpiece.
   * Tram align block parallel to X axis.

   <br>
2. hd: Mount workpiece  

   * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded, minimum 4.5" long.
   * Determine $\Delta_B$, the amount that topZ exceeds the ideal tickness
     * Measure actual workpiece thickness $T_B$: topZ to botZ (near endB) 
        - Expected to be greater than 312.5mil (5/16")
        - Measured $T_B$: <ins>...     ...</ins> mil
     * Compute $\Delta_B$: amount that $T_B$ exceeds 5/16"
        - Computed $\Delta_B$ = $T_B$ - 312.5 = <ins>...     ...</ins> mil
     * There may be variation in the stock dimensions.  One bar 
     measures 312.5 by 313.0 mil, another measures 310.0 by 310.0. 
     As a result the value of $\Delta_B$ may range between slightly positive
     for thick material and slightly negative for thin material.
     This set of procedures _assumes the point of view_ that $\Delta_B$ is slightly positive:
     on the order of a few mils. Material that is thin to begin with will
     be biased in the opposite direction.  If you have the choice then
     choose the orientation that sets $\Delta_B$ nearest to zero.

   * Position workpiece against block with 1" exposed left (operator pov)
   * Add hold-downs using >5/16" rear support block (do not use step-blocks) 
     - sideC is facing up.
     - topZ is facing away from operator.
     - endB (raw) is facing to left.

   ![]({{image-dir}}pocket1-comp.png)
   Workpiece on table. 
   Arrow always points toward topZ surface.
 
   <br>
3. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  
   This step leaves an $\approx$ 1/16" lip, at botZ, beyond the endB surface
   depending on the initial quality of the workpiece end.

   ``` 
   Examine the 3/8em cutting edges under the microscope.
   Any burrs or metal adhesions must be removed.
   ```

   * Retract Z and change tool.
   * Gross center X Y at exposed end of workpiece
   * Set Z=0 at sideC using ohmmeter
   * Retract Z to -15mil from 0
   * Gross adjust Y for cutter centered, X cut just beyond uncut endB
   * Advance Z to 50mil from -15mil
   * Set X=0 at uncut endB using ohmmeter
   * Retract X to -15mil from 0
   * Retract Gross adjust Y beyond topZ
   * Advance X to 250mil from -15mil
   * Set Y=0 at topZ using ohmmeter
   * Retract Y to -50mil from 0
   * Retract Z to -15mil from 50mil
   * Retract X to -15mil from 250mil
   * Advance Z to 260mil from -15mil
   * Advance X to 0 from -15mil
   * Turn on mill
   * Repeat to goal of squared workpiece endB (total depth of cut depends on roughness of endB)
     - Advance X in 5mil steps for $\approx$10mil total depth of cut and visually smooth.
     - Full Sweep Y: advance to Y=700mil (_SC_), retract to Y=-50mil(_NCC_) 
       + 12 turns
   * Turn off mill

   ![]({{image-dir}}pocket2-comp.png)
   Squared endB with remaining lip

   <br>
4. 3/8em: Reduce to 1/4" width of anchor to establish sideA

   ```
   Note: This procedure yielded good results but may
   be overly cautious. Consider future simplification.
   Perhaps an initial thinning with the fly cutter would speed the procedure.
   ```
   * Retract Z
   * Remove workpiece and deburr edge at endB / sideC
     - it must be able to lay flat on table
   * Measure $\delta$, sideA to sideC near endB using caliper
     - It should be damn close to 5/16" = 312.5mil; expect undersize maybe 310mil
     - Measured $\delta$: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;    ...</ins> mil
     - Appearance: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;   ...</ins>
   * Clean table surface
   * Rotate and mount workpiece 180$^{\circ}$, endB lip is uppermost. 1" exposed.
     - sideA is facing up.
     - endB is facing to left.
     - botZ is facing away from operator
   * Measure $\eta$, height from table to sideA near endB using dial indicator
     - It should be damn close to $\delta$ as measured above.
     - Measured $\eta$: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;    ...</ins> mil
     - Appearance: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;   ...</ins>
   * Gross center Y, tool overlaps both sides of workpiece (above surface of sideA)
   * Adjust X visually to $\approx$50mil beyond lip at endB of workpiece, lower Z as needed.
   * Set X=0 (gross)
   * Advance X to 450mil from 0 (9 turns)
   * Set Z=0 at sideA using ohmmeter
   * Retract Z to -15mil from 0
   * Retract X to -50mil from 450mil (10 turns)
   * Advance Z to 5mil from -15mil
   * Add cutting oil
   * Turn on mill
     - Full Sweep X: (advance to X=750mil, retract to X=-50mil) 
       + 16 turns of X knob from X=-50 to X=750
   * Turn off mill
     - Appearance of fresh surface should be very smooth.  Else there is a problem with 3/8em. 

   <br>
   * $\boldsymbol{\xi}$ &nbsp; &nbsp;  _begin sub-procedure_
   * X is at -50mil
   * Retract Z and Y to make room for dial indicator.  Do not move X.
   * Clean area then measure $\eta$, height from table to fresh cut using dial indicator
     - Measure at $\approx$ 1/8" intervals starting near endB
     - Measured $\eta$: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;    ...</ins> mil
     - Appearance: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;   ...</ins>
     - Evaluate planarity; is it level across entire cut?
   * Compute new Z goal, $\zeta$, where $\zeta$ = $\eta$ - **260** mil
   * Remove dial indicator
   * Gross center Y,Z tool overlaps both sides of workpiece (above surface of sideA)
   * Advance X to 450mil from -50mil (10 turns)
   * Set Z=0 at sideA using ohmmeter
   * Retract Z to -15mil from 0
   * Retract X to -50mil from 450mil (10 turns)
   * Advance Z to 0 from -15mil

   * Incrementally lower Z, in 10mil increments to goal of $\zeta$ mil
     - Add cutting oil
     - Turn on mill
     - Full Sweep X: (advance to X=750mil, retract to X=-50mil)
       * 16 rotations of X knob from X=-50 to X=750
     - Turn off mill
     - Brush tool cutting edge and surrounding area to clear debris
     - Visually inspect quality of fresh surface of sideA

   * Continue from $\boldsymbol{\xi}$ if desired

   * _end of sub-procedure_ $\boldsymbol{\xi}$

   <br>
   Extreme caution for the next step is warranted.  Something may be 
   wrong with my mill but I found that cuts are consistently several
   thou deeper than Z knob would indicate. My first attempt yielded
   $\zeta$ = 8.5mil, but I chose to be conservative and advance Z 
   by only 5mil and then repeating $\xi$ to find $\eta$ = 250.5mil.
   This was the desired goal, but had I used $\zeta$ = 8.5mil I would 
   have overshot the 250mil limit and been very sad.

   * Repeat from $\boldsymbol{\xi}$ with modifications:
     - This is the final setting of sideA
     - Compute final Z goal, $\zeta$, where $\zeta$ = $\eta$ - **250** mil
     - Perhaps use 5mil increments, or less
     - Confirm using sub-process $\boldsymbol{\xi}$

   <br>
   * Z is at sideA with $\eta \approx$250mil above table and 
   a crescent cut that's 5/16" - 1/4" $\approx$62.5mil tall.
   * X is at -50mil
   * Set Z=0 (sideA is now at 0)
   * Advance Z to 50mil from 0
   * Set X=0 cut at endB using ohmmeter
   * Retract X to -15mil from 0
   * Retract Z to -100mil from 50mil to clear crescent cut. (3 turns)
   * Retract Y just beyond botZ
   * Set Y=0 cut (gross)
   * Retract Y to -50mil from 0
   * Advance X to 750mil from -15mil (15$^+$ rotations)
   * Advance Z to -65mil from -100mil
   * Turn on mill (penultimate)
     - Incrementally advance Z, in 10mil increments to goal of -5mil
     - Full Sweep Y: (advance to Y=600mil, retract to Y=-50mil)  
       * 14 turns of X knob from Y=-50 to Y=600
   * Turn off mill
   * Incrementally advance Z, in 0.5mil increments to flush with sideA
     - Turn on mill (ultimate)
     - Full Sweep Y: (advance to Y=600mil, retract to Y=-50mil)  
       * 14 turns of X knob from Y=-50 to Y=600
     - Turn off mill
     - Visual inspect for evidence of crescent.
     - Repeat until crescent is just removed. 

   <br>
   * Retract Z and Y to make room for dial indicator.  Do not move X.
   * Clean area then measure $\eta$, height from table to fresh cut using dial indicator
     - Measure at $\approx$ 1/8" intervals starting near endB
     - Measured $\eta$: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;    ...</ins> mil
     - Appearance: <ins>...  &nbsp; &nbsp; &nbsp; &nbsp;   ...</ins>
     - Evaluate planarity; is it level across entire cut?

   <br>
   * Remove workpiece from table
   * Measure $\delta$: sideA to sideC; should be 250mil +5 -0
     - Measure at $\approx$ 1/4" intervals starting near endB
     - Measured $\delta$: <ins>... &nbsp; &nbsp; &nbsp; &nbsp;  ...</ins> mil
     - Appearance: <ins>...    ...</ins>

   <br>

   ![]({{image-dir}}pocket3-comp.png)
   SideA is facing upwards.

   <br>
5. ef: Locate hole for adhesive arch

   Much of the area around this hole will be cut away in subsequent steps.


   * Retract Z and change tool
   * Rotate workpiece 180$^{\circ}$
     - lay 1/8" x 1/2" spacer against tram (protect table from drill tip)
     - stack workpiece on spacer
     - expose 1" workpiece beyond tram bar
     - sideA is facing downwards.
     - sideC is facing upwards.
     - botZ is facing operator.
     - endB is facing to left.
   * Gross adjust Y for tool centered on sideC, X for tool beyond endB
   * Gross set Z=0 at sideC
   * Advance Z to 150mil from 0 
   * Turn on mill
   * Jog X so as to advance X to indicate endB edge via ef
   * Set X=0
   * Turn off mill
   * Retract X to -15mil from 0
   * Advance Y beyond botZ
   * Advance X to 195mil from -15mil
   * Turn on mill
   * Jog Y so as to retract Y to indicate botZ edge via ef
   * Set Y=0
     - Note: this sets the hole height wrt botZ
   * Turn off mill
   * Advance Y to +15mil from 0
   * Retract Z to -50mil from 150mil
   * Retract Y to -210mil from +15mil
   * X,Y are now centered on screw hole

   <br>
6. 1/8cd: Cut guide divot for drill in topZ
    * Retract Z and change tool
    * Advance Z and locate Z=0 with ohmmeter
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

      | Z | Z | Z | Z | Z |
      |---|---|---|---|---|
      | 50|100|150|200|250|

    * Retract Z to -15mil from 250mil
    * Turn off mill

    ![]({{image-dir}}pocket4-comp.png)
    Hole for arch. SideA facing down, sideC facing up. Spacer not shown.

    <br>
8. 1/4em: Gross Cut tongueA (10mil oversize)  
   Gross cut of tongueA and tongueC yields gross tongue width 140 + 10 + 10 = 160mil

    * Retract Z and change tool.
    * Rotate workpiece 90$^{\circ}$ such that sideA is facing away from operator
      - remove spacer
      - expose 1" workpiece beyond tram bar
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
      - Gross retract Y for cut beyond sideA
      - Advance X to 250mil from -15mil
      - Set Y=0 cut at sideA using ohmmeter
      - Retract X to 150mil from 250mil
      - Advance X to 170mil from 150mil
      - Retract Y to -15mil from 0
    * X is at 170mil, Z at 50mil
    * Advance Z to 300mil from 50mil (5 rotations)
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=45mil:
      - Advance Y in 5mil steps to goal of 45mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=170mil(_NCC_) (4rot & 20mil)

      | Y | Y | Y | Y | Y | Y | Y | Y | Y | Y | Y |
      |---|---|---|---|---|---|---|---|---|---|---|
      | -5|  0|  5| 10| 15| 20| 25| 30| 35| 40| 45|

    * Turn off mill
    * Retract Y to -15mil from 45mil
    * Retract X to -15mil from 170mil (3rot & 15mil)
    * Retract Z to -15mil from 300mil (6rot)

    <br>
9. 1/4em: Gross Cut tongueC (10mil oversize)  
   Gross cut of tongueA and tongueC yield gross tongue width 140 + 10 + 10 = 160mil

    * Advance Y to 550mil from -15mil (cut beyond sideC)
    * Advance X to 250mil from -15mil (15mil & 5rot)
    * Advance Z to 50mil from -15mil
    * Set Y=0 cut at sideC using ohmmeter (retraction bias)
    * Advance Y to +15mil from 0
    * Advance Z to 300mil from 50mil (5rot)
    * Retract X to -50mil from 250mil (6rot)
    * Retract Y to +5mil from +15mil (remove backlash)
    * Turn on mill
    * Repeat to goal of Y=-45mil:
      - Retract Y in 5mil steps to goal of -45mil
      - Full Sweep X: advance to X=170mil (_SC_), retract to X=-50mil(_NCC_) (4rot & 20mil)  

      | Y | Y | Y | Y | Y | Y | Y | Y | Y | Y | Y |
      |---|---|---|---|---|---|---|---|---|---|---|
      | +5|  0| -5|-10|-15|-20|-25|-30|-35|-40|-45|

    * Turn off mill
    * Retract X to -50mil (20mil & 4rot)
    * Advance Y to +15mil from -45mil
    * Retract Z to -15mil from 300mil

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
      - Note: this sets botT wrt botZ
    * Retract Z to -15mil
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from -15mil 
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideC
    * Advance X to 300mil from -15mil (15mil & 6rot) 
    * Set Y=0 @cut using ohmmeter
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Retract X to 0 from 300mil (6rot)
    * Advance X to 60mil from 0
    * Advance Z to 0 from -15mil
    * Turn on mill (this step is where botT is established)
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=450mil, retract to Y=-50mil) (10rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 80|

      ( there will be no obvious breakthrough into hole )
    * Turn off mill
    * Retract Z to -15mil from 80mil
    * Y is at -50mil
    * Advance X to 175mil from 60mil
    * Turn on mill (this step is to remove excess material; stop at 80$^-$mil, just short of botT)
      - Incrementally advance Z, in 10mil increments to goal of 80$^-$mil
      - Full Sweep Y: (advance to Y=450mil, retract to Y=-50mil) (10rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 80$^-$|

      ( hole breakthrough appears at Z=60 )
    * Turn off mill
    * Retract Z to -15mil from 80mil

    ![]({{image-dir}}pocket7-comp.png)
    Lower surface of tongue tip

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
    * Retract Z to 50mil from 100mil 
    * Advance Z to 70mil from 50mil 
    * Advance X to 165mil from -15mil (15mil & 3rot & 15mil)
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 110mil
      - Full Sweep Y: (advance to Y=450mil, retract to Y=-50mil) (10rot) 

      | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|
      | 70| 80| 90|100|105|110|

    * Turn off mill
    * Retract Z to -15mil from 110mil
    ```
    Note that the ideal of setting the cantilever surface tangent to
    the hole assumes the 1/8em tool is actually 125mil diameter.
    In practice it may be less than that. This will leave a small step
    at the hole. This step, which indicates that the cantilever is
    slightly thick, is desirable and should be left as is.
    ```

    ![]({{image-dir}}pocket8-comp.png)
    Cantilever at lower end of tongue

    <br>
12. 3/8em: Establish topT, the upper surface of the tongue

    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Gross center X,Y
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -50mil (knob indicates 0)
    * Reset Z=0 by $\Delta_b$ (see step 2)
      - Reset knob to indicate -$\Delta_B$ (watch the sign!)
      - Advance Z by $\Delta_B$ to 50mil indication
        * (Z=0 is now $\Delta_B$ **below** topZ; watch out!)
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from -50mil 
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideA
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 150mil from -15mil (15mil & 3rot)
    * Advance Z to +2.5mil from -50mil
    * Turn on mill
    * Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (15rot) (9rot sufficient?) 
    * Turn off mill
    * Retract Z to -50mil from 2.5mil
    * Y is at -50mil
    * X is at 150mil

    ![]({{image-dir}}pocket9-comp.png)
    Upper surface of tongue is topT

    <br>
13. 3/8em: Establish topK, the upper surface of the key anchor

    * X,Y,Z is 150,-50,-50 mil (Z=0 @topT is already biased by $\Delta_B$)
    * Advance X to 475mil from 150mil (6rot & 25mil)
    * Advance Z to 0 from -50mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (15rot) (14rot sufficient?) 

      | Z | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 75| 80|

    * Turn off mill
    * Retract Z to -50mil from 80mil
    * Advance X to 600mil from 475mil (25mil & 2rot)
    * Advance Z to 0 from -50mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (15rot) 

      | Z | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 75| 80|

    * Turn off mill
    * Retract Z to -50mil from 80mil
    * Advance X to 750mil from 600mil (3rot)
    * Advance Z to 0 from -50mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (15rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 75| 80|

    * Turn off mill
    * Retract Z to -50mil from 80mil

    ![]({{image-dir}}pocket10-comp.png)
    Upper surface of anchor is topK

    <br>
14. 1/8rem: Fillet on rear of tongue

    ```
    1/8rem bit has 10thou radius.

    Beware of bolt on hold-down next to tool.
    ```

    * Retract Z and change tool
    * Gross center X,Y over top of tongue
    * Set Z=0 at topK using ohmmeter
    * Retract Z to -15mil from 0
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from -15mil
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideA
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -15mil from 50mil
    * Advance X to 210mil from -15mil
    * Advance Z to 0 from -15mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80$^-$mil
        - watch carefully for fillet at Z contact with upper surface of anchor
      - Full Sweep Y: (advance to Y=450mil, retract to Y=-50mil) (10rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|---|---|
      |  0| 10| 20| 30| 40| 50| 60| 70| 75| 80$^-$| visual|

    * Turn off mill
    * Retract Z to -15mil from 80mil

    ![]({{image-dir}}fillet0-comp.png)
    Rear of tongue with fillet at topK

    <br>
15. ef: Locate screw hole center 

    * Retract Z and change tool
    * Deburr rough edges along upper surface of anchor and tongue
    * Gross adjust X,Y for tool just beyond tongue at endB
    * Gross set Z=0 at topT
    * Advance Z to 50mil from 0 
    * Turn on mill (reduce speed)
    * Jog X so as to advance X to indicate endB position via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 50mil
    * Retract Y beyond sideA
    * Advance X to 100 + 285 = 385mil from -15mil
    * Gross center Y
    * Gross set Z=0 at topK
    * Retract Z to -15mil from 0
    * Retract Y beyond sideA
    * Advance Z to 50mil from -15mil
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
    * Drill 180mil pocket by advancing Z to 180mil, 50mil at a time, adding oil each thrust

      _In my kit there is a 4-40 flathead screw whose shank has been shortened.
      The resulting screw is 179mil head to toe. It can be used to test the
      depth of the hole chamfer to be produced in the subsequent step.
      In this step the pocket has been extended from 100mil to 180mil in depth._
    * Retract Z to -15mil from 100mil
    * Turn off mill

    ![]({{image-dir}}pocket12-comp.png)
    Pocket for screw hole

    <br>
18. 1/4cs (1-flute 82$^{\circ}$): Countersink the screw hole  
    __These dimensions are suitable for all variations of HIF6, the standard HIF44 screw and its substitue #4-40 screw.__
    * The top diameter of the chamfer target is 225mil.  It should not exceed 230mil and
      must be less than the 250mil width of the key.

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

    For #4-40 to be flush with key: $S$=125mil, $D$=250mil, $\theta$=82$^{\circ}$:  

    <p style="text-align: center;">
      $H = \frac{250-125}{2 tan(\frac{82}{2})} \approx 72mil$
    </p>

    In practice setting $D$ to be equal to the width of the key is an inappropriate target
    and results in the edges of the key being subject to deformation induced by 
    tightening the screw.  Fortunately, in situ, there is adequate room for the top of 
    the screw to be proud of the key by 20 to 30mil.  Empirical results with the
    actual tooling and hardware suggests a value of $H$ on the order of 50mil.
    The foreshortened indicator screw head should be proud of the key by no less than 20mil. 

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Retract X and Y then advance back to 385,225 (remove backlash)
    * Advance Z to ohmmeter contact at topK 

      _The tip of cs will be inside the screw hole.  
      The contact will be at the rim of the screw hole.  
      It may help to manually jog tool rotation as Z is advanced.  
      Try to avoid cutting the rim of the screw hole at this time._

      _In my kit there is a #4-40 flathead screw whose shank has been shortened.
      The resulting screw is 179mil head to toe. It can be used to test the
      depth of the hole chamfer produced here.
      Note that in the final assembly the top of the screw will be proud of the 
      top of the guide key by 20mil or so. If the chamfer is too deep then
      it will extend beyond the edge of the key.  This is not desirable._
    * Set Z=0
    * Retract Z to -100mil from 0
    * Turn on mill
    * Advance Z to 0 from -100mil
    * Repeat to goal of Z=50mil (or screw head proud by no less than 20mil):
      - Advance Z towards 50mil from -100mil 
      - Retract Z to -100mil 
      - Check depth progress with foreshortened #4-40 screw and 20mil feeler gauge.
      - Apply some judgement
      - Leave Z at -100mil once depth is established  

    * Turn off mill

    ![]({{image-dir}}chamfer0-comp.png)
    Countersink for screw hole

    * Measure: large diameter of cs should be $\approx$225mil
      + Diameter Measured: <ins>...     ...</ins> mil
    * Test fit with #4-40 flathead screw should be proud $\approx$25mil
      + Proud Measured: <ins>...     ...</ins> mil

    <br>
19. 3/8em: Establish botK, the lower surface of the key anchor

    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing operator.
      - sideC is facing away from operator.
      - botT, botZ is facing up.
      - endB is facing to left.
    * Gross center X,Y for cutting edge above tongue topT
    * Set Z=0 at botT using ohmmeter
      - Z=0 is referenced to the bottom of the tongue!
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Retract Z to -100mil from 50mil
    * Advance X to 460mil from -15mil
    * Advance Z to -80mil from -100mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (14rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|
      |-80|-70|-60|-50|-40|-30|-20|-10|  0|
      | 10| 20| 30| 40| 50| 60| 70| 75| 80|

    * Turn off mill
    * Retract Z to -100mil from 80mil
    * Advance X to 600mil from 460mil
    * Advance Z to -80 from -100mil
    * Turn on mill
      - Incrementally advance Z, in 10mil increments to goal of 80mil
      - Full Sweep Y: (advance to Y=700mil, retract to Y=-50mil) (14rot) 

      | Z | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|---|
      |-80|-70|-60|-50|-40|-30|-20|-10|  0|
      | 10| 20| 30| 40| 50| 60| 70| 75| 80|

    * Turn off mill
    * Retract Z to -100mil from 80mil

    ![]({{image-dir}}pocket13-comp.png)
    Bottom surface of anchor at botK

    <br>
20. 1/8em: Final Cut tongueA

    Final cut of tongueA and tongueC yields tongue width 140mil
    ```
    Alternative: For final width of 150mil use delta Y = 50 instead of 55mil
    ```

    * Retract Z and change tool.
    * Dismount workpiece
    * Deburr
    * Measure: topT to botT, should be 230mil
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>
    * Measure: topK to botK, should be 70mil
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Using ohmmeter establish Z=0 @topT, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed endB of workpiece
      - Set Z=0 at topT using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 250mil from -15mil
      - Advance Z to 100mil from 50mil
      - Set Y=0 cut at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * Retract X to 100mil from 250mil
    * Advance X to 148mil from 100mil
    * Advance Z to 275mil from 100mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Advance Y to 35mil from -15m (with mill running)
    * Repeat to goal of Y=55mil:
      - There will be a screech!
      - Advance Y in 5mil steps to goal of 55mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=148mil(_NCC_) (3rot & 48mil)

      | Y | Y | Y | Y | Y |
      |---|---|---|---|---|
      | 40| 45| 50| 53| 55|

    * Turn off mill
    * Retract Y to -15mil from 55mil
    * Retract X to -15mil from 148mil
    * Retract Z to -15mil from 275mil

    <br>
21. 1/8em: Final Cut tongueC 

    Final cut of tongueA and tongueC yield tongue width 140mil

    * Advance Y to 450mil from -15mil (cut beyond sideC)
    * Advance X to 250mil from -15mil
    * Advance Z to 100mil from -15mil
    * Set Y=0 cut at sideC using ohmmeter
    * Advance Y to +15mil from 0
    * Advance Z to 275mil from 100mil
    * Retract X to 100mil from 250mil
    * Advance X to 148mil from 100mil
    * Turn on mill
    * Retract Y to -35mil from 15mil
    * Retract X to -50mil from 148mil
    * Repeat to goal of Y=-55mil:
      - There will be a screech!
      - Retract Y in 5mil steps to goal of -55mil
      - Full Sweep X: advance to X=148mil (_SC_), retract to X=-50mil(_NCC_) (3rot & 48mil)  

      | Y | Y | Y | Y | Y |
      |---|---|---|---|---|
      |-40|-45|-50|-53|-55|

    * Turn off mill
    * X is at -50mil
    * Advance Y to +15mil from -55mil
    * Retract Z to -15mil from 275mil

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
      - Overhang material 1-1/2" from end of tram bar.
      - Short stud is required for left hold-down. 
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
    * Retract X to 100mil from 200mil
    * Advance X to 130mil from 100mil
    * Advance Z to -2mil from -50mil 
    * Turn on mill
      - Incrementally advance Z, in 2mil increments to goal of 10mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil) (9rot) 

      | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|
      |  0|  2|  4|  6|  8| 10|

    * Turn off mill
    * Retract Z to -15mil from 10mil

    ![]({{image-dir}}pocket16-comp.png)
    Adhesive overflow channel

    <br>
23. 1/8em: Preliminary dado for key cut off.

    Goal is 20mil deep dado in botK surface

    * Retract Z and change tool.
    * Gross center X,Y over botK
    * Advance Z to just above botT
    * Set Z=0 (gross)
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 500mil from -15mil (15mil & 8rot)
    * Gross center Y over botK
    * Set Z=0 at botK using ohmmeter
    * Retract Z to -15mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Advance X to 560mil from 500mil
    * Advance Z to -5mil from -15mil 
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of 20mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil) (10rot) 

      | Z | Z | Z | Z | Z |
      |---|---|---|---|---|
      |  0|  5| 10| 15| 20|

    * Turn off mill
    * Retract Z to -15mil from 20mil

    ![]({{image-dir}}pocket17-comp.png)
    Preliminary dado for cut off

    <br>
24. 1/8em: Penultimate dado for key cut off.

    Goal is 40mil deep dado in topK surface

    * Dismount workpiece; deburr prior to final separation
    * Rotate workpiece 180$^{\circ}$
      - sideA is facing away from operator.
      - sideC is facing operator.
      - topZ is facing up.
      - endB is facing to left.
    * Gross center X,Y over topK
    * Advance Z to just above topT
    * Set Z=0 (gross)
    * Adjust X to just beyond endB of workpiece
    * Advance Z to 50mil from 0
    * Set X=0 cut at endB using ohmmeter
    * Retract X to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance X to 500mil from -15mil (15mil & 10rot)
    * Gross center Y over topK
    * Set Z=0 at topK using ohmmeter
    * Retract Z to -50mil from 0
    * Retract Y just beyond sideC
    * Set Y=0 cut (gross)
    * Retract Y to -50mil from 0
    * Advance X to 560mil from 500mil
    * Advance Z to -5mil from -50mil 
    * Add a blob of putty between tongue and table 
      - to provide support and containment of key after cutoff
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of 35mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil) (9rot)  

      | Z | Z | Z | Z | Z | Z | Z | Z |
      |---|---|---|---|---|---|---|---|
      |  0|  5| 10| 15| 20| 25| 30| 35|

    * Turn off mill
    * Z is at 35mil

    ![]({{image-dir}}pocket18-comp.png)
    Penultimate dado for cut off

    <br>
25. 1/8em: Ultimate dado for key cut off.

    Goal is additional 15mil deep dado in topK surface to separate guide key from workpiece.
    Putty should prevent key from falling into tool or elsewhere.

    * Z is at 35mil
    * Turn on mill
      - Incrementally advance Z, in 5mil increments to goal of $\approx$50mil
      - Full Sweep Y: (advance to Y=400mil, retract to Y=-50mil) (9rot)  

      | Z | Z | Z |
      |---|---|---|
      | 40| 45| 50|

    * Turn off mill
    * Retract Z to -15mil from 50mil

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
``` bash 
$ site assets/mini/project/su.piston.position/guideKey/series-8/
$ mkdir thumbs.tmp
$ cd thumbs.tmp
$ cp ../*.png .
$ magick mogrify -format png -thumbnail 200x200 *.png
-or-
$ mkdir thumbs.tmp
$ magick mogrify  -format gif -path thumbs.tmp -thumbnail 200x200 *.jpg
```
{% endcomment %}

See post: [preparing images update]({{ site.url | append: "/2026/04/07/notebook.html" }})

``` bash 
$ site assets/mini/project/su.piston.position/guideKey
$ mkdir dirty.tmp
$ # copy directories of dirty png files to dirty.tmp, i.e. myPart
$ cd dirty.tmp/myPart
$ # create new clean files, they will have -comp added to name 
$ for f in `ls -1 *.png`; do echo $f; compPNG $f; done
$ # create the clean directory
$ mkdir series-8
$ # move the clean files to the clean directory
$ mv *-comp.png series-8
$ # now create thumbnail files
$ mkdir thumbs
$ cd thumbs
$ cp ../*-comp.png .
$ magick mogrify -format png -thumbnail 200x200 *.png
$ # check the work
$ cd ../.. # back to dirty.tmp/myPart/ 
$ tree
$ # put the files in place 
$ mkdir ../../series-8/thumbs.tmp
$ mv myPart/thumbs/*.png ../../series-8/thumbs.tmp
$ rmdir myPart/thumbs
$ mv *.png ../../series-8/
```
