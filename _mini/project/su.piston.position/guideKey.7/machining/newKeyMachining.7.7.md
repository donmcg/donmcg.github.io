---
layout: default
title: Rev.7 Guide Key 7 Machining Proposal
tip: machining guide key 7, rev 7
date:   2026-04-17 01:00:00 -0700
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

New Key Machining Proposal Revision 7:
* Proposal 7.7 based on
    [Machining 7.6]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/machining/newKeyMachining.7.6.html" }})
    and
    [Finishing 7.6]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/machining/newKeyFinishing.7.6.html" }})

* Produces fourth physical newKey, aka brassKey8

* Use drawing newKey.6 
  - The newKey.6 drawing reduces final tongue width to 140mil.

<br>
* Primary changes from Rev. 6:
  - Elimination of the use of tool dimensions for locations of cuts.
  - Switch from 60$^{\circ}$ BSW 1/8-40 to 82$^{\circ} $#4-40 screw
  - Merge Machining and Finishing procedures
  - Eliminate penultimate steps
  - Postpone setting tongueB (waiting to establish this dimension)
  - Multiple flips of workpiece:
    + mount 1st topZ up
      * cut endB
      * gross cut wide tongue to 160mil
      * cut screw hole with countersink
    + mount flip topZ down
      * cut tongueF, tongue thinned to 100mil
      * cut dado and chamfer between heel and tongue
    + mount flip topZ up
      * finish cut tongue width to 140mil
      * finish cut tongueB end (postpone this step, endB remains, 150mil)
      * cut topside dado for cutoff
    + mount flip topZ down
      * cut dado to detach part

<br>
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
hd | 4" x 10" Mill Tooling Plate | hold-down  
vise | 4" x 10" Mill Tooling Plate | milling vise, Sherline 3551
ef | End Mill Holder | edge finder, Starrett 827A
3/8em | End Mill Holder | 3/8" end mill
1/4em | End Mill Holder | 1/4" end mill
1/8em | 1/8" collet | 1/8" end mill
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

{% comment %} definition lists do not work as advertised...
In the following steps:  
_`SC:`_
: Standard Cut  

_`CC:`_
: Climb Cut   

_`NCC:`_
: No Climb Cut, No cut made despite climb direction motion

A 
: my Add

<dl>
  <dt>B term</dt>
  <dd>my Blist</dd>
</dl>
{% endcomment %}

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

{% comment %}
{% include figure.html
           img-dir=image-dir
           img-file='brassKey4Machine-comp.png'
           alt='brassKey4 in mill'
           caption='BrassKey4 at Machining. Workpiece mounted on table.'
%}
{% endcomment %}

<br>
1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd: Mount workpiece  

    * Workpiece: 0.25" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 7/8" exposed left (operator pov)
    * Add hold-downs using >1/4" rear support block (do not use step-blocks) 

    <br>
3. 3/8em: Square off end of workpiece to set endB  
    Rigid 3/8em required to achieve suitable results.  
    This step leaves an $\approx$50mil lip, at botZ, beyond the endB surface
    depending on the initial quality of the workpiece end.

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
4. 1/4em: Gross Cut tongueA (10mil oversize)  
   Gross cut of tongueA and tongueC yield gross tongue width 140 + 10 + 10 = 160mil

    * Retract Z and change tool.
    * Using ohmmeter establish Z=0 @topZ, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed end of workpiece
      - Set Z=0 at topZ using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 225mil from -15mil
      - Set Y=0, carefully, cut at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * X is at 225mil
    * Advance Z to 150mil from 50mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=45mil:
      - Advance Y in 5mil steps to goal of 45mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=225mil(_NCC_)  
    * Turn off mill
    * Retract Y to -15mil from 45mil
    * Retract X to -15mil from 225mil
    * Retract Z to -15mil from 150mil

    <br>
5. 1/4em: Gross Cut tongueC (10mil oversize)  
   Gross cut of tongueA and tongueC yield gross tongue width 140 + 10 + 10 = 160mil

    * Advance Y to 550mil from -15mil (cut beyond sideC)
    * Advance X to 225mil from -15mil
    * Advance Z to 50mil from -15mil
    * Set Y=0, carefully, cut at sideC using ohmmeter
    * Advance Y to +15mil from 0
    * Advance Z to 150mil from 50mil
    * Retract X to -15mil from 215mil
    * Retract Y to +5mil from +15mil (remove backlash)
    * Turn on mill
    * Repeat to goal of Y=-45mil:
      - Retract Y in 5mil steps to goal of -45mil
      - Full Sweep X: advance to X=225mil (_SC_), retract to X=-15mil(_NCC_)  
    * Turn off mill
    * X is at -15mil
    * Advance Y to +15mil from -45mil
    * Retract Z to -15mil from 150mil
    * Deburr:
      - Freecut: Advance Z to -1mil. X and Y as needed to deburr top edges.

    <br>
    * Measure: tongueA to tongueC should be 160mil
      - Measured: <ins>...     ...</ins> mil
      - Appearance: <ins>...    ...</ins>

    <br>
    ```
    <br>
6.  ef: Locate screw hole
    * Retract Z and change tool
    * Gross adjust X,Y for tool centered on tongue beyond endB
    * Gross set Z=0 at topZ
    * Advance Z to 150mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB position via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond sideA
    * Advance X to 470mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate sideA position via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 150mil
    * Advance Y to 225mil from -15mil
    * X,Y are now centered on screw hole

    <br>
7. 1/8cd: Cut guide divot for drill in topZ
    * Retract Z and change tool
    * Advance Z and locate Z$\approx$0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 20mil cutting divot for drill
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
9.  1/4cs (1-flute 82$^{\circ}$): Countersink the screw hole  
    __These dimensions are for the substitue #4-40 screw.__
    * The top diameter of the chamfer must exceed ???mil
      to accomodate the #4-40 screw.  
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

    For #4-40: $S$=125mil, $D$=250mil, $\theta$=82$^{\circ}$:  

    <p style="text-align: center;">
      $H = \frac{250-125}{2 tan(\frac{82}{2})} \approx 72mil$
    </p>

    In practice the 72mil depth should be considered the maximum limit.
    A #4-40 x 1/4" screw will drop into the hole and serve as a 
    progress indicator.  The ideal is the top of the screw is flush with topZ.

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Advance Z to ohmmeter contact  
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
    * Measure: large diameter of cs should be $\approx$250mil
      + Diameter Measured: <ins>...     ...</ins> mil

    <br>
17. 3/8em: Fly cut top surface to deburr
    * Retract Z and change tool
    * Gross center X,Y for cut edge above tongue & beyond countersink
    * Advance Z to ohmmeter touch top surface.
    * Set Z=0 at topZ
    * Retract Z to -15mil from 0
    * Freecut: Advance Z to -1mil.
    * Turn on mill
    * X and Y as needed to deburr top
    * Turn off mill
    * Clean up as necessary.  
 
    <br>
18. Flip the workpiece over to work from botZ of brassKey.
    * Dismount workpiece
    * Measure: tongue width should be 160mil
      - Final Measured: <ins>...     ...</ins> mil
    * Clean up with smooth file and super fine diamond sharpener (1200)
    * Rotate 180deg so that topZ is downwards against table, botZ is up.
    * Remount with endB facing left (in the same direction as before.)
      - 3/4" overhang

    <br>
19. 3/8em: Rabbet to remove botZ lip and expose endB surface

    Goal here is to remove the remaining 50mil lip at the end of the 
    workpiece and expose the endB surface for X alignment in a subsequent step.  
    The remaining ledge from this step will be removed with the subsequent fly cut.

    * Advance Z and locate Z$\approx$0
    * Retract Z to -50mil
    * Gross align X,Y at part center, Z above uncut surface 
    * Advance Z to ohmmeter touch top surface.
    * Set Z=0 at botZ
    * Retract Z to -15mil from 0
    * Gross align Y beyond sideA
    * Advance Z to 20mil from -15mil
    * Set Y=0 at sideA
    * Advance Y to 315mil from 0 ($\approx$ center of tongue)
    * Gross align X for tool to just overhang-intersect endB tip
    * Set X=0 at overhang
    * Retract Y to -15mil from 315mil
    * Turn on mill  
      Repeat until endB edge is just exposed:
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

    * Retract X from 0 to -50mil
    * Advance Y to 315mil from -15mil ($\approx$ center of tongue)  
    * Retract X to -50mil from 0
    * Retract Z to -30mil from -15mil
    * Advance Z to -10mil from -30mil
    * Turn on mill
      - Incrementally lower Z, in 10mil increments to goal of 150mil
      - Full Sweep X: (advance to X=700mil, retract to X=-50mil)  
    * Turn off mill
    * X is at -50mil
    * Z is at 150mil
    * Retract Y to -15mil from 315mil 

    <br>
21. 3/8em: Square off semi-circular step at the advanced X end of part.  
    Step needs to be squared off so that remaining bar material is square.

    * Retract Z to 145mil from 150mil 
    * Retract Y to -50mil from -15mil 
    * Advance X to 600mil from -50mil  
    * Turn on mill
      Note: this cut is on the bar, not the workpiece, leaves 15mil for cut-off dado.
      - Incrementally advance X, by 15mil, to goal of 710mil
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)   
    * Advance Z to 149mil from 145mil
    * Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)
    * Turn off mill
    * Retract Z to -15mil from 149mil  
    * Retract X to -15mil from 710mil  
    * Retract Y to -15mil

    <br>
22. 1/8em: Dado between anchor and tongue (gives sensor room to bend) 

    Goal is 20mil deep dado in tongueF surface

    * Retract Z and change tool.
    * Gross center X Y Z
    * Advance Z to ohmmeter touch
    * Set Z=0 at tongueF
    * Retract Z to -15mil from 0
    * Retract X for tool beyond endB
    * Advance Z to 50mil from 0
    * Advance X to ohmmeter touch endB 
    * Set X=0 at endB
    * Retract Y beyond sideA (well beyond tongueA)
    * Advance to X=350mil
    * Gross align Y beyond sideA with $\approx$15mil clearance
    * Set Y=0 at position with clearance 
    * Retract Y to -15mil from 0
    * Retract Z to -15mil from 50mil
    * Retract X to 200mil from 350mil
    * Advance X to 255mil from 200mil (remove backlash)
    * Turn on mill
    * Advance Z to 10mil from -15mil
    * Advance Y to 440mil cutting shallow dado
    * Advance Z to 20mil from 10mil
    * Retract Y to -15mil completing 20mil dado
    * Turn off mill
    * Retract Z to -15mil from 20mil

    <br>
23. 5/16cs 6-flute 82$^{\circ}$: chamfer Dado at tongue edge

    > This is a new version of this step that relies more on 
    > visual adjustment since the 5/16cs tools have a blunt 
    > tip that isn't easily centered.

    Goal is 15mil chamfer of 20mil dado edge

    * Retract Z and change tool.
    * Gross center X Y Z over tongueF
    * Set Y=0 at gross center
    * Advance Z to ohmmeter touch
    * Set Z=0 at tongueF
    * Retract Z to -15mil from 0
    * Advance X to gross center over dado
    * Advance Z to 5mil
    * Retract X to ohmmeter touch cut at edge of dado adjacent to tongue
    * Set X=0 at dado edge
    * Turn on mill
    * __Watch carefully__ and retract Y to -100mil, just barely cutting edge.
    * __Watch carefully__ and advance Y to +100mil, just barely cutting edge.
    * Goal is to create Z=10mil chamfer: 
      - Incrementally advance Z, by 5mil, to goal of 15mil
      - Full Sweep Y: retract to Y=-100mil(_SC_), advance to Y=+100mil (_NCC_),  
    * Retract X to -2mil 
      - Full Sweep Y: retract to Y=-100mil(_SC_), advance to Y=+100mil (_NCC_),  
    * Retract X again and sweep Y if desired __Use your judgement__
    * Retract Z to -15mil from 15mil
    * Turn off mill

    <br>
18. Flip the workpiece over to work from topZ of brassKey.
    * Dismount workpiece
    * Measure: tongue width should be 160mil (redundant)
      - Final Measured: <ins>...     ...</ins> mil
    * Clean up with smooth file and super fine diamond sharpener (1200)
    * Rotate 180deg so that botZ is downwards against table, topZ is up.
    * Remount with endB facing left (in the same direction as before.)
      - 3/4" overhang

    <br>
4. 1/8em: Finish Cut tongueA 
   Finish cut of tongueA and tongueC for tongue width of 140mil

    * Retract Z and change tool.
    * Using ohmmeter establish Z=0 @topZ, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed end of workpiece
      - Set Z=0 at topZ using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 252mil from -15mil
      - Set Y=0, carefully, cut at sideA using ohmmeter
      - Retract Y to -15mil from 0
    * X is at 252mil
    * Advance Z to 150mil from 50mil
    * Advance Y to -5mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=55mil:
      - Advance Y in 5mil steps to goal of 55mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=252mil(_NCC_)  
    * Turn off mill
    * Retract Y to -15mil from 55mil (offset from sideA)
    * Retract X to -15mil from 252mil
    * Retract Z to -15mil from 150mil

    <br>
5. 1/8em: Finish Cut tongueB
   Finish cut of tongueB for tongue length of 140mil
   > This step is optional until desired tongue length is established.

    * Retract Y to -50mil from -15mil
    * Advance Z to 150mil from 50mil
    * Turn on mill
    * Repeat to goal of X=10mil:
      - Advance X in 5mil steps to goal of 10mil
      - Full Sweep Y: advance to Y=300mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Advance Y to -15mil from -50mil
    * Retract X to -15mil from 10mil
    * Retract Z to -15mil from 150mil

    <br>
5. 1/8em: Finish Cut tongueC
   Finish cut of tongueA and tongueC for tongue width of 140mil

    * Advance Y to 400mil from -15mil (cut beyond sideC)
    * Advance X to 252mil from -15mil
    * Advance Z to 50mil from -15mil
    * Set Y=0, carefully, cut at sideC using ohmmeter
    * Advance Y to +15mil from 0
    * Advance Z to 150mil from 50mil
    * Retract X to -15mil from 252mil
    * Retract Y to +5mil from +15mil (remove backlash)
    * Turn on mill
    * Repeat to goal of Y=-55mil:
      - Retract Y in 5mil steps to goal of -55mil
      - Full Sweep X: advance to X=252mil (_SC_), retract to X=-15mil(_NCC_)  
    * Turn off mill
    * X is at -15mil
    * Advance Y to +15mil from -55mil
    * Retract Z to -15mil from 150mil

    <br>
14. Caliper: Verify final tongue width is 140mil wide  
    * Measure: tongueA to tongueC tongue width should be 140mil
      - Final Measured (mounted): <ins>...     ...</ins> mil
      - Appearance: <ins>...         ...</ins>

    <br>
15. 1/8em: Top side dado at anchor heel for cut off.  
    > Note: I can find no reference to confirm or deny that cutting a dado
    > in this manner is an appropriate use of an end mill.  

    Cut 20mil deep dado on anchor heel:

    * Retract Y beyond sideA (well beyond tongueA)
    * Advance X to 695mil from -15mil (assuming tongueB was __NOT__ cut)
    * Advance Z to 50mil from -15mil
    * Set Y=0 cut at sideA using ohmmeter
    * Retract Y to -50mil from -15mil
    * Retract Z to -15mil
    * Advance Z to 10mil from -15mil
    * Turn on mill
    * Advance Y to 450mil from -50mil (_SC_)
    * Retract Y to -50mil from 450mil (_NCC_)
    * Advance Z to 20mil
    * Advance Y to 450mil from -50mil (_SC_)
    * Retract Y to -50mil from 450mil (_NCC_)
    * Turn off mill
    * Retract Z to -15mil from 20mil
    * Retract X to -15mil from 695mil
    * Deburr:
      - Freecut: Advance Z to -1mil. X and Y as needed to deburr top edges.

    <br>
18. Flip the workpiece over to work from botZ of brassKey.
    * Dismount workpiece
    * Measure: tongue width should be 140mil (redundant)
      - Final Measured: <ins>...     ...</ins> mil
    * Clean up with smooth file and super fine diamond sharpener (1200)
    * Rotate 180deg so that topZ is downwards against table, botZ is up.
    * Remount with endB facing left (in the same direction as before.)
      - 3/4" overhang

    <br>
24. 1/8em: Deep dado to meet top-side dado resulting in cutoff at anchor end

    Goal is new dado to meet opposing 20mil dado, cutting off brassKey

    * Using ohmmeter establish Z=0 @tongueF, X=0 @endB and Y=0 @sideA
      - Gross center X Y at exposed end of workpiece
      - Set Z=0 at tongueF using ohmmeter
      - Retract Z to -15mil from 0
      - Gross adjust X for cut beyond endB (assuming tongueB was __NOT__ cut)
      - Advance Z to 50mil from -15mil
      - Set X=0 cut at endB using ohmmeter
      - Retract X to -15mil from 0
      - Gross adjust Y for cut beyond sideA
      - Advance X to 695mil from -15mil (assuming tongueB was __NOT__ cut)
      - Set Y=0 at sideA using ohmmeter
    * Retract Y to -50mil from 0
    * Retract Z to -50mil from 50mil
    * X is at 695mil
    * Clamp two-hole wood block using hex bolts across key as a hold down
    for final cutoff.
    * Advance Z to 10mil from -50mil
    * Turn on mill  
      Goal is to meet 20mil opposing dado resulting in cut off at Z$\approx$80mil.
      - Incrementally advance Z, by 10mil, to goal of 80mil
      - Half Sweep Y: (retract to Y=-50mil or advance to Y=450mil)
    * Turn off mill
    * Retract Y to -50mil
    * Retract Z to -250mil
    * Clean up brassKey with smooth file and super fine diamond sharpener (1200)

<br>

---

<br>

### Final dimensions, mils: (assuming tongueB was __NOT__ cut)

| __FEATURE__ | __TARGET, mil__ | __ACTUAL__ |
| ----------- |:----------:| ----------:|
tongue width | 140 | ...     ... 
tip to heel | 570 | ...     ...
heel to hole edge | 137.5 | ...     ...
tip to hole edge | 257.5 | ...     ...
hole diameter | 125 | ...     ...
side 1 to hole | 62.5 | ...     ...
side 2 to hole | 62.5 | ...     ...
side 1 to side 2 | 250 | ...     ...
key thickness | 100 | ...     ...

### Notes:


{% comment %}
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[markdown syntax](https://learn-markdown.github.io/assets/markdown-cheatsheet.pdf)
{% endcomment %}
