---
layout: default
title: Rev.6 Guide Key 7 Machining Procedure
tip: machining guide key 7, rev 6
date:   2026-03-30 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
  blog: project/su.piston.position/guideKey.7/machining
---

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/
{% endcapture %}

Last update {{ page.date | date: "%d %b %Y" }}.

Revision 6:
* Actual procedure followed based on rev5 proposal.

* Produced third physical newKey

* Use drawing newKey.5
  - The newKey.5 drawing adds guidepoint for tongue length trim.


<br>
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
hd | 4" x 10" Mill Tooling Plate | hold-down  
3/8em | End Mill Holder | 3/8" end mill
1/4em | End Mill Holder | 1/4" end mill
1/8em | 1/8" collet | 1/8" end mill
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

      Hence an outside cut around the part would start on sideA, continue
      around endB, and finish along sideC.
```

<br>
`In the following steps:`  
_`SC:`_`Standard Cut`  
_`CC:`_`Climb Cut`  
_`NCC:`_`No Climb Cut, No cut made despite climb direction motion`

<br>
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
  * tongueF is the bottom side of the tongue opposing topZ
```

```
Diameters:
  Problems with tongue dimensions led to the realization
  that the end mills are smaller, in diameter, than ideal.
  This is normal and due to manufacturing tolerance or sharpening.

    Measured:
    1/8em 123mil
    1/4em ??
    3/8em 373mil

  In the next iteration of this procedure, a different approach
  will be taken to locate the critical edges and hole position
  of the tongue.

```

<br>
1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, offset by one hole.
    * Tram adjust block parallel to X axis

    <br>
2. hd: Mount workpiece  

    * Workpiece: 0.25" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 7/8" exposed left (operator pov)
    * Add hold-downs using >1/4" rear support block (do not use step-blocks) 

    <br>
3. 3/8em: Square off end of workpiece to set endB

    Rigid 3/8em required to achieve suitable results.
    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust X,Y for cutter near center of endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Advance X to 250mil from -15mil
    * Set Y=0 at sideA using ohmmeter
    * Retract Y to -50mil from 0
    * Retract X to -15mil from 250mil
    * Advance Z to 200mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

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
4. 1/4em: Gross Cut tongueA (10mil oversize)

    * Retract Z and change tool.
    * Using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
      - Gross center X,Y
      - Z=0 is topZ
      - X=0 is endB 
      - Y=0 is sideA
      - Gross center X Y at exposed end of workpiece
      - Set Z=0 at topZ using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X,Y for cutter near center of endB
      - Advance Z to 50mil from -15mil
      - Set X=0 at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y beyond sideA
      - Advance X to 200mil from -15mil
      - Set Y=0 at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * Advance Z to 150mil from 50mil
    * Advance X to 235mil from 200mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=40mil:
      - Advance Y in 5mil steps to goal of 40mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=235mil(_NCC_)  
    * Turn off mill
    * Leave Y at 40mil
    * Retract X to -15mil from 235mil
    * Retract Z to -15mil from 150mil

    <br>
5. 1/4em: Gross cut tongueC (10mil oversize)  
    _This step erroneously assumes 1/4em is exactly 125mil diameter._

    * X is at -15mil
    * Z is at -15mil
    * Advance Y from 40mil to 460mil (10mil beyond final tongue edge)
    * Turn on mill
    * Advance Z to 0 from -15mil
    * Repeat to goal of Z=150mil:
      - Advance Z incrementally, 15mil per, towards goal Z=150mil
      - Full Sweep X: advance to X=235mil(_SC_), retract to X=0mil (_NCC_)  
    * Turn off mill
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 150mil
    * Leave Y at 460mil
    * Deburr:
      - Freecut: Advance Z to -1mil. X and Y as needed to deburr top edges.

    <br>
    * Measure: tongueA to tongueC should be 170mil
      - Measured: <ins>...176....</ins> mil
      - Appearance: <ins>...good...</ins>

    <br>
    ```
    In the following steps, that establish penultimate tongue width and  
    center the drill the screw hole, to avoid Y backlash:
      Y will ONLY be advanced (+ direction)
      X will retract to -15mil before next advance
      Penultimate tongue goal: 150 + 5 + 5 = 160mil
      Finished tongue width goal: 155mil
      Polished tongue width goal: 150mil
              (post milling to fit actual piston groove)
    ```

    <br>
6.  1/8em: Penultimate cut tongueA
    * Retract Z and change tool
    * Using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
      - Z=0 is topZ
      - Retract Z to -15mil, Retract Y beyond sideA, Advance Z to 50mil
      - Y=0 is sideA 
      - Retract X beyond endB, Advance Y to 200mil
      - X=0 is endB
    * Retract X to -15mil, Y to -15mil, Z to -15mil.
    * Advance Z to 150mil from -15mil
    * Advance X to 213mil from -15mil
    * Advance Y to 30mil from -15mil
    * Turn on mill
    * Repeat to goal Y = 45mil: (leaves 5mil excess of finished on tongueA)
      - Advance Y in 5mil steps to goal of 45mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=213mil(_NCC_)  
    * Retract Z to -15mil from 150mil
    * Turn off mill

    <br>
7. 1/8cd: Locate screw hole and make divot in topZ
    * Y is at 45mil
    * X is at -15mil
    * Retract Z and change tool
    * Advance Y from 45mil to 187.5mil
    * Advance X from -15mil to 432.5mil
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 20mil cutting hole center location divot
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill screw hole
    * Retract Z and change tool
    * Advance Z and locate Z$\approx$0  
      (Use ohmmeter contact with divot as Z=0)
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill 200mil hole by advancing Z to 200mil, 50mil at a time, adding oil each thrust
    * Retract Z to -15mil from 200mil
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
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Advance Z to ohmmeter contact  
      _The tip of cs will be inside the screw hole.  
      The contact will be at the rim of the screw hole.  
      It may help to manually jog tool rotation as Z is advanced.  
      Try to avoid cutting the rim of the screw hole._
    * Set Z=0
    * Retract Z to -15mil from 0
    * Turn on mill
    * Advance Z to 60mil from -15mil 
    * Retract Z to -15mil from 60mil
    * Turn off mill
    * Retract X to -15mil from 432.5mil
    * Measure: large diameter of cs should be $\approx$194mil
      + Diameter Measured: <ins>...194.5...</ins> mil

    <br>
10. 1/8em: Penultimate cut tongueC 
    Goal: 160mil penultimate tongue width (5mil oversize)
    _This step erroneously assumes 1/4em is exactly 125mil diameter._

    * Retract Z and change tool
    * Advance X to 150mil from -15mil
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil
    * Retract X to -15mil from 150mil
    * Advance Y to 330mil from 187.5mil (leaves 5mil excess of finished on side 2)
    * Turn on mill
    * Repeat to goal Z=150mil:
      - Advance Z incrementally, 15mil per, towards goal Z=150mil
      - Full Sweep X: advance to X=213mil(_SC_), retract to X=0mil (_NCC_)  
      _Error was made here, one sweep, at Z=60, advanced too far. Not critical._
    * Turn off mill
    * Retract X to -15mil
    * Retract Z to -100mil from 150mil

    <br>
11. Caliper: Verify penultimate tongue is 160mil wide  
    Expected penultimate tongue width is 160mil, desired finished is 155mil  
    * Measure: tongue width should be 160mil
      + PenultimateMeasuredWidth: <ins>...164...</ins> mil  
      _Difficult to measure in-situ. 160-165 range. => use conservative 160mil_ 
      + Appearance: <ins>...clean, no chatter...</ins>
      + Compute __delT__ = PenultimateMeasuredWidth - 155 : <ins>...5...</ins> mil
      + Compute __delT/2__ : <ins>...2...</ins> mil (Round down to nearest mil)

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
12. 1/8em: Finish cut tongueC    
    _This step erroneously assumes 1/4em is exactly 125mil diameter._

    * X is at -15mil
    * Y is at 330mil from previous step
      - Compute __Y2__ = 330 - delT/2: <ins>...328...</ins> mil
      - Compute __Y2retract__ = Y2 - 15mil: <ins>...313...</ins> mil
    * Retract Y to __Y2retract__
    * Advance Z to 150mil from -100mil
    * Turn on mill
    * Advance Y to __Y2__ from __Y2retract__ (eliminates backlash)
    * Full Sweep X: advance to X=254mil(_SC_), retract to X=0mil (_NCC_)  
    * Turn off mill
    * Leave Z at 150mil

    <br>
13. 1/8em: Finish cut tongueA  

    * Y is at _Y2_ 
    * X is at -15mil
    * Z is at 150mil
    * Compute __Y1__ = 45 + delT/2: <ins>...47...</ins> mil
    * Retract Y to 30mil from __Y2__
    * Advance X to 254mil from -15mil
    * Turn on mill
    * Advance _slowly_ Y to __Y1__ from 30mil
    * Retract X to -15mil from 254mil (_SC_)
    * Turn off mill
    * Retract Y to -15mil from __Y1__
    * Retract Z to -100mil from 150mil

    <br>
14. Caliper: Verify final tongue width is 155mil wide  
    * Measure: tongue width should be 155mil
      - Final Measured: <ins>...159...</ins> mil
      - Appearance: <ins>...beautiful...</ins>
      - Compute __delF__ = FinalMeasured - 155 : <ins>...4...</ins> mil  
      _This __delF__ is too large due to failure to consider actual diameter of 1/8em._  
      _Also, it's difficult to make this measurement in-situ._

    <br>
15. 1/8em: Top side dado for cut off.  
    > Note: I can find no reference to confirm or deny that cutting a dado
    > in this manner is an appropriate use of an end mill.  

    Cut 20mil deep dado on anchor heel:
    * Retract Y to -15mil
    * Advance X to 695mil from -15mil 
    * Advance Z to 10mil from -15mil
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
16. 3/8em: Gross cut rabbet to reduce tongue length by 50mil, establishing tongueB 
    >
    > This step produces the surface designated as tongueB.
    > This step reduces the tongue length from 150mil to 100mil.  
    > The nominal tongue length is 80mil, subject to fitting.  
    > Tongue length prior to this cut: 150mil  
    > Nominal length in-situ (unconfirmed): 80mil  
    > Length reduction this cut: 50mil  
    > Length after this cut: 100mil  
    > Becomes 20mil oversize beyond nominal of 80mil
    >
    > Fitting and measuring will yield a better
    > idea of what the nominal tongue length should be.  
    > It may be better to make a fixture solely for trimming
    > the tongue length, and perhaps the width polishing...

    Cut rabbet to create tongueB surface:
    * Retract Z and change tool
    * Gross center X Y
    * Locate Z=0 at topZ
    * Retract Z to -15mil from 0
    * Retract Y behind sideA
    * Advance Z to 50mil from -15mil
    * Locate Y=0 at sideA
    * Retract Y to -15mil
    * Retract X beyond endB
    * Advance Y to 350mil from -15mil
    * Locate X=0 at endB
    * Retract X to -15mil
    * Retract Y to -15mil from 350mil
    * Advance X to 50mil from -15mil
    * Retract Z to 0 from 50mil
    * Turn on mill
    * Repeat to goal Z=120mil:
      - Advance Z incrementally, 15mil per, towards goal Z=120mil
      - Full Sweep Y: advance to Y=450mil(_SC_), retract to Y=50mil (_NCC_)  
    * Turn off mill
    * Retract Z to -15mil from 120mil
    * Retract Y to -15mil from 50mil
    * Retract X to -15mil from 50mil

    <br>
17. 3/8em: Fly cut top surface to deburr
    * Advance Y to 315mil from -15mil
    * Freecut: Advance Z to -1mil. X and Y as needed to deburr top
    * Clean up as necessary.  
 
    <br>
18. Flip the workpiece over to work on bottom of guideKey.
    * Dismount workpiece
    * Measure: tongue width should be 155mil
      - Final Measured: <ins>...160...</ins> mil
    * Clean up with smooth file and super fine diamond sharpener (1200)
    * Rotate 180deg so that topZ is downwards against table, botZ is up.
    * Remount with endB facing left (in the same direction as before.)
      - 3/4" overhang

    <br>
19. 3/8em: Rabbet endB to expose tongueB surface

    Goal here is to expose the tongueB surface for X alignment in a subsequent step.  
    The rabbet cut in this step will be removed on the subsequent fly cut

    * Advance Z and locate Z$\approx$0
    * Retract Z to -50mil
    * Gross align Y at part center, X above uncut surface 
    * Advance Z to ohmmeter touch top surface.
    * Set Z=0 at botZ
    * Retract Z to -15mil from 0
    * Gross align Y beyond sideA
    * Advance Z to 20mil from -15mil
    * Set Y=0 at sideA
    * Advance Y to 315mil from 0
    * Gross align X for tool to just overhang-intersect tongueB tip
    * Set X=0 at overhang
    * Retract Y to -15mil from 315mil
    * Turn on mill  
      Repeat until tongueB edge is just exposed:
      - Incrementally advance Z, by 15mil, to goal of Z$\approx$60mil  
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Retract Z to -15mil  
    * Retract Y to -15mil (if at 450mil)  
    * Leave X at 0

    <br>
20. 3/8em: Fly cut to reduce remaining key thickness to 100mil
    and establish the tongueF surface.  

    Goal here is to remove a total of 150mil of material
    for a 100mil final thickness of key.  
    Also leaves room for 1/8" anchor cutoff dado

    * Advance Y to 315mil (end mill Y-centered over part)  
    * Retract X such that tool edge is perhaps 50mil gap to tongueB
    * Advance Z to 20mil from -15mil
    * Set X=0 at tongueB
    * Retract X to -50mil from 0
    * Retract Z to -10mil from 20mil
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of 150mil
      - Full Sweep X: (advance to X=650mil, retract to X=-50mil)  
    * Turn off mill
    * X is at -50mil
    * Z is at 150mil
    * Retract Y to -15mil from 315mil 

    <br>
21. 3/8em: Square off semi-circular step at the advanced X end of part.  
    Step needs to be squared off so that remaining bar material is square.

    * Retract Z to 145mil from 150mil 
    * Retract Y to -50mil from -15mil 
    * Advance X to 550mil from -50mil  
    * Turn on mill
      Note: this cut is on the bar, not the workpiece
      - Incrementally advance X, by 15mil, to goal of 665mil
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)   
    * Advance Z to 149mil from 145mil
    * Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)
    * Turn off mill
    * Retract Z to -15mil from 149mil  
    * Retract X to -15mil from 665mil  
    * Retract Y to -15mil

    <br>
22. 1/8em: Dado between anchor and tongue  

    Goal is 20mil deep dado in tongueF surface

    * Retract Z and change tool.
    * Gross center Y X
    * Advance Z to ohmmeter touch
    * Set Z=0 at tongueF
    * Retract Z to -15mil from 0
    * Retract X for tool beyond tongueB
    * Advance Z to 50mil from 0
    * Advance X to ohmmeter touch tongueB 
    * Set X=0 at tongueB
    * Retract Y beyond sideA (well beyond tongueA)
    * Advance to X=350mil
    * Gross align Y beyond sideA with $\approx$15mil clearance
    * Set Y=0 at clearance position 
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
23. 5/16cs 6-flute 60$^{\circ}$: chamfer Dado at tongue edge

    > I faked this step because 5/16cs does not actually
    > have a sharp tip at all. Instead I just visually
    > aligned and made the cuts.
    > This step should be rewritten for a future procedure.

    Goal is 18mil chamfer of 20mil dado edge

    __Does it matter which angle for the 5/16cs?  Not really__

    * Retract Z and change tool.
    * Retract X to 125mil from 205mil
    * Advance X to 142mil from 125mil (remove backlash)
    * Advance Y to 100mil from -15mil  
    <br>
    __==> non-existent tip of cs is now over dado edge, 0.5mil offset towards tongue__

    * Visually confirm position and correct if needed
    * Advance Z to ohmmeter contact (tip of cs will overhang edge)
    * Set Z=0 at tongueF
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

    &&&
    <br>
24. 1/8em: Deep dado to meet top-side dado resulting in cutoff at anchor end

    Goal is new dado to meet opposing 20mil dado, cutting off guideKey

    * Retract Z and change tool.
    * Advance Y to 100mil from -15mil
    * Advance X to 625mil from -15mil
    * Advance Z to ohmmeter touch
    * Set Z=0 at tongueF
    * Retract Z to -15mil from 0
    * Retract Y to -50mil from 100mil
    * Clamp two-hole wood block using hex bolts across key as a hold down
    for final cutoff.
    * Turn on mill  
      Goal is to meet 20mil opposing dado resulting in cut off at Z$\approx$80mil.
      - Incrementally advance Z, by 10mil, to goal of 80mil
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
tongue width | 155 | ...163.5... 
tip to heel | 520 | ...508...
heel to hole edge | 137.5 | ...172...
tip to hole edge | 257.5 | ...210...
hole diameter | 125 | ...125...
side 1 to hole | 62.5 | ...71...
side 2 to hole | 62.5 | ...58...
side 1 to side 2 | 250 | ...250.5...
key thickness | 100 | ...99.5...

### Notes:

*  These results are not particularly satisfactory.

*  At step 16 somehow I goofed and resulted in setting tongueB too short 
   by 257.5 - 210 = 47.5mil.

*  Tongue width excess appears to be due to 1/8em actual diameter of 123mil.
   This adds 4 mils to the penultimate cuts.  Step 11 measured 164 instead of 160.

*  Finished goal was 155mil, measured 163.5.  Problems with steps 12 & 13?

*  Even though the tongue is shorter than the target value, it actually 
   compares favorably to the standard key tongue, so may work well enough for now.

*  Why is heel too long?  Heel dado was based on uncut endB. Step 15.
   Did I mis-count and place it at 695 + 50 = 745?  This does not seem
   to be the explanation.


{% comment %}
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[markdown syntax](https://learn-markdown.github.io/assets/markdown-cheatsheet.pdf)
{% endcomment %}
