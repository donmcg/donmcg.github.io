---
layout: default
title: Proposal Rev.1 - Series 8 Assembly Fixture Component Machining 
tip: machining assembly fixture parts for series 8, rev 1
date:   2026-06-22 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ assyFix.8 ] # applies to chapter level
  blog: project/su.piston.position/assyFixture/series-8-assyfix
---

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/assyFixture/series-8/thumbs/
{% endcapture %}
{% comment %}
  use thumbs for actual printing...  saves a lot of paper!
  {{site.url}}/assets/mini/project/su.piston.position/assyFixture/series-8/thumbs/
{% endcomment %}

Last update {{ page.date | date: "%d %b %Y" }}.

Series 8 Assembly Fixture Component Machining Proposal Revision 1:

Instructions for machinging the brass components of the series 8 assembly fixture.

{% comment %}
Proposal 8.1 based on
    [Rev.7 Guide Key 8 Machining Proposal]({{ site.url | append: "/mini/project/su.piston.position/guideKey/series-7-guidekey/newKeyMachining.7.7.html" }})
{% endcomment %}

### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
sp | 1/8" x 1/2" Sacrificial Plate | 360-H02 brass stock spacer 
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
3/16hs | 3/16" collet | 3/16" 140$^{\circ}$ hole spotting bit
1/4cs | 1/4" collet | 1/4" countersink (1-flute 82$^{\circ}$)
5/16cs6 | 1/4" collet | 5/16" countersink (6-flute 60$^{\circ}$)
5/16cs1 | 1/4" collet | 5/16" countersink (1-flute 82$^{\circ}$)
127rmr | 3mm collet | 127mil reamer (straight-flute 140$^{\circ}$)
caliper | hand | digital caliper
ss | hand | sabre saw fitted with fine brass-cutting blade
{% comment %}
1/8cd | 1/4" collet | 1/8" center drill (not for drill centering!)
{% endcomment %}

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
```

Depth of divot, $H$, for bit of diameter $D$, using $\theta = 140^{\circ}$ 3/16" spotting bit:

<p style="text-align: center;">
      $H = \frac{D}{2} {tan(90^{\circ}-\frac{\theta}{2})}$
</p>

Minimum depth with hole bit of diameter $D$=1/8" for all holes in this procedure.

<p style="text-align: center;">
      $H_{min} = \frac{1}{8} \frac{tan(20^{\circ})}{2}$ = 22.7mil
</p>

Maximum depth with spotting bit of diameter $D$=3/16"

<p style="text-align: center;">
      $H_{max} = \frac{3}{16} \frac{tan(20^{\circ})}{2}$ = 34.1mil
</p>

These steps choose $H$=25mil as the target depth for divots.

### Base 

1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd / sp: Mount workpiece  

    * Spacer: 1/8" x 1/2" sacrificial plate against block, flush at left
    * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left 
      ($\approx$1/4" overhanging end of sacrificial plate)
    * Add hold-downs using 1/2" rear support block (do not use step-blocks) 
      - sideC is facing up.
      - topZ is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}Base/pocket0upC-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    ![]({{image-dir}}Base/BaseHolddown-comp.png)
    Holddown must be positioned for hole machining
 
    <br>
2. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  

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
    * Set Y=0 at sideC using ohmmeter
    * Retract Y to -50mil from 0
    * Retract X to -15mil from 250mil
    * Advance Z to 350mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    <br>
3. ef: Locate 1st hole for guide mount

    * Retract Z and change tool
    * Gross adjust Y for tool centered on sideC, X for tool beyond endB
      - sideC is facing up.
    * Gross set Z=0 at sideC
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond topZ
    * Advance X to 350mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate topZ edge via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 250mil from -15mil
    * X,Y are now centered on screw hole

    <br>
7. 3/16hs: Cut guide divots for drill in sideC

   See introduction for calculation of divot depth.

    * Retract Z and change tool
    * Advance Z to sideC using ohmmeter
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract X and Y then advance back to 350,250 (remove backlash)
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting first divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill
    * Advance X to 850mil from 350mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting second divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill guide screw holes
    * Retract Z and change tool
    * Advance Z to sideC divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill first 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill
    * Retract X to 300mil from 850mil
    * Advance X to 350mil from 300mil
    * Add cutting oil
    * Turn on mill
    * Drill second 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill


    ![]({{image-dir}}Base/pocket1-comp.png)
    Guide screw holes

    <br>
3. ef: Locate 1st hole for topZ

    * Retract Z and change tool
    * Rotate workpiece 90$^{\circ}$
      - Note that drilling to come must avoid hold-downs:
        + Mark a pen line 895mil from endB on topZ
        + Position such that left hold-down is centered on mark
      - topZ is facing up.
      - endB is facing to left.
      - sideA is facing away from operator
    * Gross adjust Y for tool centered on topZ, X for tool beyond endB
      - sideC is facing up.
    * Gross set Z=0 at topZ
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond topZ
    * Advance X to 600mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate topZ edge via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 250mil from -15mil
    * X,Y are now centered on first hole

    <br>
7. 3/16hs: Cut guide divots for drill in topZ

   See introduction for calculation of divot depth.

    * Retract Z and change tool
    * Advance Z to topZ using ohmmeter
    * Set Z=0
    * Retract Z to -15mil from 0
    * Retract X and Y then advance back to 600,250 (remove backlash)
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting first divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 1390mil from 600mil; jumping over hold-down 
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting second divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 1700mil from 1390mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting third divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 2100mil from 1700mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting fourth divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 2600mil from 2100mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting fifth divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill screw holes and stud pockets
    * Retract Z and change tool
    * Advance Z to topZ divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil

    * Turn on mill
    * Drill 200mil stud pocket by advancing Z to 200mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 2050mil from 2600mil
    * Advance X to 2100mil from 2050mil
    * Add cutting oil
    * Turn on mill
    * Drill 340mil screw pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 1650mil from 2100mil
    * Advance X to 1700mil from 1650mil
    * Add cutting oil
    * Turn on mill
    * Drill 340mil screw pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 1350mil from 1700mil
    * Advance X to 1390mil from 1350mil
    * Turn on mill
    * Drill 200mil stud pocket by advancing Z to 200mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 550mil from 1390mil; jumping over hold-down 
    * Advance X to 600mil from 550mil
    * Add cutting oil
    * Turn on mill
    * Drill 340mil screw pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    ![]({{image-dir}}Base/pocket3-comp.png)
    TopZ screw holes and stud pockets

    <br>
9.  1/4cs (1-flute 82$^{\circ}$): Countersink the screw hole  

    ```
    The top diameter of the chamfer must exceed ???mil to fully recess
    the #4-40 screw.  In practice the 72mil depth should be considered
    the maximum limit. A #4-40 x 1/4" screw will drop into the hole and
    serve as a progress indicator.  The ideal is the top of the screw is
    slightly recessed.
    ```

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Retract X and Y then advance back to XXX,YYY (remove backlash)
      - X is at 550mil
      - Y is at 250mil
    * Advance Z to ohmmeter contact at topZ in hole
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

    * Advance X to 1700mil from 550mil
    * Advance Z to ohmmeter contact at topK in hole 
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

    ![]({{image-dir}}Base/chamfer0-comp.png)
    Countersinks for screw holes


    <br>
3. ef: Locate existing hole in botZ

    * Retract Z and change tool
    * Rotate workpiece 180$^{\circ}$
      - botZ is facing up.
      - endB is facing to left.
      - sideA is facing operator
    * Gross adjust Y for tool centered on botZ, X for tool beyond endB
    * Gross set Z=0 at botZ
    * Advance Z to 100mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Advance Y beyond sideA
    * Advance X to 500mil from -15mil
    * Turn on mill
    * Jog Y so as to retract Y to indicate sideA edge via ef
    * Turn off mill
    * Set Y=0
    * Advance Y to +15mil from 0
    * Retract Z to -50mil from 100mil
    * Retract Y to -250mil from +15mil
    * Advance X to 2100mil from 500mil
    * X,Y are now centered on hole (hopefully)

    <br>
9.  1/4cs (1-flute 82$^{\circ}$): Countersink the screw hole  

    * Retract Z and change tool
    * Minimally deburr screw hole entry without enlarging hole using hand held 82$^{\circ}$6-flute cs.
    * Retract X and Y then advance back to XXX,YYY (remove backlash)
      - X is at 2100mil
      - Y is at -250mil
    * Advance Z to ohmmeter contact at botZ in hole
      _Use your judgement for alignment_
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

    ![]({{image-dir}}Base/chamfer1-comp.png)
    Countersink for screw hole

    <br>
22. ss: Base cut off.

    * Retract Z and remove workpiece.
    * Mark cut line at 2-13/16"
    * Mount workpiece in bench vise
    * Cut with sabre saw beyond cut linea
    * If desired, raw end can be restored with em as in step 3

    ![]({{image-dir}}Base/BasePinScrew-comp.png)
    Base fitted with screws and studs 


<br>

---
### Anvil 

1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd / sp: Mount workpiece  

    * Spacer: 1/8" x 1/2" sacrificial plate against block, flush at left
    * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left 
      ($\approx$1/4" overhanging end of sacrificial plate)
    * Add hold-downs using 1/2" rear support block (do not use step-blocks) 
      - topZ is facing up.
      - sideA is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}Anvil/pocket0-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    ![]({{image-dir}}Anvil/AnvilHolddown-comp.png)
    Holddown must be positioned for hole machining
 
    <br>
2. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Set Y=0 
    * Retract Y to -50mil from 0
    * Advance Z to 350mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Set X=0 
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 350mil

    <br>
3. ef: Locate 1st hole for Anvil

    * Retract Z and change tool
    * Gross adjust Y for tool centered on topZ, X for tool beyond endB
      - topZ is facing up.
    * Gross set Z=0 at topZ
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond sideA
    * Advance X to 390mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate sideA edge via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 250mil from -15mil
    * X,Y are now centered on first screw hole at 390,250

    <br>
7. 3/16hs: Cut Anvil divots for drill in topZ

   See introduction for calculation of divot depth.

    * Retract Z and change tool
    * X,Y are now centered on first hole at 390,250
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting first divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 1100mil from 390mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting second divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 1600mil from 1100mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting third divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill Anvil screw and stud holes

    * Retract Z and change tool
    * X,Y are now centered on third hole at 1600,250
    * Advance Z to topZ divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill third 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 1050mil from 1600mil
    * Advance X to 1100mil from 1050mil
    * Add cutting oil
    * Turn on mill
    * Drill second 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 350mil from 1100mil
    * Advance X to 390mil from 350mil
    * Add cutting oil
    * Turn on mill
    * Drill first 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    <br>
8. 127rmr: Ream Anvil stud holes
    ```
    The stud holes must be large enough for the Anvil to slide...
    ```
    * Retract Z and change tool
    * X,Y are now centered on first stud hole at 390,250
    * Advance Z to topZ divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Ream pocket by advancing Z to 330mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 330mil
    * Turn off mill

    * Advance X to 1600mil from 390mil
    * Add cutting oil
    * Turn on mill
    * Ream pocket by advancing Z to 330mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 330mil
    * Turn off mill

    ![]({{image-dir}}Anvil/pocket3-comp.png)
    Anvil screw and stud holes

    <br>
2. 3/8em: Add steps on Anvil endB

   Rigid 3/8em required to achieve suitable results.  

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Set Y=0 
    * Retract Y to -50mil from 0
    * X,Y,Z are at -15,-50,-15 mil
    * Advance Z to 250mil from -15mil
    * Turn on mill
    * Repeat to goal of X=65mil total depth of cut
      - Advance X in 10mil steps for 65mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}Anvil/pocket1-comp.png)
    First step at Anvil endB

    ```
    I've had some trouble with Z accuracy and this next step depth
    is critical. So a little extra caution here to refine Z=0...
    ```
    * Advance X to 100mil from 65mil
    * Retract Z to -15mil from 250mil
    * Advance Z to -5mil from -15mil
    * Turn on ohmmeter sensing
    * Repeat to goal of barely visible cut
      - Advance Z in 1/2mil steps 
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)
      - _look and listen for contact_
    * Turn off mill
    * Set Z==0

    * Retract X to 0mil from 100mil
    * Advance X to 60mil from 0
    * Advance Z to 12mil from 0
      - _ideal is 12.5mil, but better too shallow than too deep_
    * Turn on mill
    * Repeat to goal of X=105mil total depth of cut
      - Advance X in 10mil steps for 105mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}Anvil/pocket2-comp.png)
    Second step at Anvil endB

<br>

---
### Ram 

1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd / sp: Mount workpiece  

    * Spacer: 1/8" x 1/2" sacrificial plate against block, flush at left
    * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left 
      ($\approx$1/4" overhanging end of sacrificial plate)
    * Add hold-downs using 1/2" rear support block (do not use step-blocks) 
      - topZ is facing up.
      - sideA is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}Ram/pocket0-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    ![]({{image-dir}}Ram/RamHolddown-comp.png)
    Holddown must be positioned for hole machining
 
    <br>
2. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Set Y=0 
    * Retract Y to -50mil from 0
    * Advance Z to 350mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Set X=0 
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 350mil

    <br>
3. ef: Locate 1st hole for Ram

    * Retract Z and change tool
    * Gross adjust Y for tool centered on topZ, X for tool beyond endB
      - topZ is facing up.
    * Gross set Z=0 at topZ
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond sideA
    * Advance X to 240mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate sideA edge via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 250mil from -15mil
    * X,Y are now centered on first screw hole at 240,250

    <br>
7. 3/16hs: Cut Ram divots for drill in topZ

   See introduction for calculation of divot depth.

    * Retract Z and change tool
    * X,Y are now centered on first hole at 240,250
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting first divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 950mil from 240mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting second divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 1450mil from 950mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting third divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill Ram screw and stud holes

    * Retract Z and change tool
    * X,Y are now centered on third hole at 1450,250
    * Advance Z to topZ divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill third 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 900mil from 1450mil
    * Advance X to 950mil from 900mil
    * Add cutting oil
    * Turn on mill
    * Drill second 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    * Retract X to 200mil from 950mil
    * Advance X to 240mil from 200mil
    * Add cutting oil
    * Turn on mill
    * Drill first 340mil pocket by advancing Z to 340mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 340mil
    * Turn off mill

    <br>
8. 127rmr: Ream Ram stud holes
    ```
    The stud holes must be large enough for the Ram to slide...
    ```
    * Retract Z and change tool
    * X,Y are now centered on first stud hole at 240,250
    * Advance Z to topZ divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Ream pocket by advancing Z to 330mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 330mil
    * Turn off mill

    * Advance X to 1450mil from 240mil
    * Add cutting oil
    * Turn on mill
    * Ream pocket by advancing Z to 330mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 330mil
    * Turn off mill

    ![]({{image-dir}}Ram/pocket1-comp.png)
    Ram screw and stud holes

    <br>
2. 3/8em: Add step on Ram endB

    * Retract Z and change tool.
    * Rotate workpiece 180$^{\circ}$
      - botZ is facing up.
      - endB is facing to left.
      - sideA is facing operator
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at botZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideC
    * Set Y=0 
    * Retract Y to -50mil from 0
    * X,Y,Z are at -15,-50,-15 mil
    * Advance X to 310mil from -15mil
    * Advance Z to -10mil from -15mil
    * Turn on mill
    * Repeat to goal of Z=70mil total depth of cut
      - Advance Z in 10mil steps for 70mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}Ram/pocket2-comp.png)
    Step at Ram endB

<br>

---
### Guide 
<br>

1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd / sp: Mount workpiece  

    * Spacer: 1/8" x 1/2" sacrificial plate against block, flush at left
    * Workpiece: 1/8" x 1/2" Brass Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left 
      ($\approx$1/4" overhanging end of sacrificial plate)
    * Add hold-downs using >1/4" rear support block (do not use step-blocks) 
      - sideC is facing up.
      - topZ is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}Guide/pocket0-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    <br>
3. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at sideC using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond topZ
    * Set Y=0 
    * Retract Y to -50mil from 0
    * Advance Z to 150mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Set X=0 
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 150mil

    <br>
3. ef: Locate 1st hole for Guide

    * Retract Z and change tool
    * Gross adjust Y for tool centered on sideC, X for tool beyond endB
      - sideC is facing up.
    * Gross set Z=0 at topZ
    * Advance Z to 50mil from 0 
    * Turn on mill
    * Jog X so as to advance X to indicate endB edge via ef
    * Turn off mill
    * Set X=0
    * Retract X to -15mil from 0
    * Retract Y beyond topZ
    * Advance X to 475mil from -15mil
    * Turn on mill
    * Jog Y so as to advance Y to indicate sideA edge via ef
    * Turn off mill
    * Set Y=0
    * Retract Y to -15mil from 0
    * Retract Z to -50mil from 50mil
    * Advance Y to 450mil from -15mil
    * X,Y are now centered on first screw hole at 475,450

    <br>
7. 3/16hs: Cut Guide divots for drill in topZ

   See introduction for calculation of divot depth.

    * Retract Z and change tool
    * X,Y are now centered on first hole at 475,450
    * Set Z=0 at sideC using ohmmeter
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting first divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    * Advance X to 975mil from 475mil
    * Add cutting oil
    * Turn on mill
    * Advance Z to 25mil cutting second divot for drill
    * Retract Z to -15mil from 20mil
    * Turn off mill

    <br>
8. 1/8sd: Drill Guide screw holes

    * Retract Z and change tool
    * X,Y are now centered on third hole at 975,450
    * Advance Z to sideC divot using ohmmeter
      (Use ohmmeter contact with divot as Z=0)
    * Set Z=0
    * Retract Z to -15mil from 0
    * Add cutting oil
    * Turn on mill
    * Drill second 150mil pocket by advancing Z to 150mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 150mil
    * Turn off mill

    * Retract X to 450mil from 975mil
    * Advance X to 475mil from 450mil
    * Add cutting oil
    * Turn on mill
    * Drill first 150mil pocket by advancing Z to 150mil, 50mil at a time,
      adding oil each thrust
    * Retract Z to -15mil from 150mil
    * Turn off mill

    ![]({{image-dir}}Guide/pocket1-comp.png)
    Guide with screw holes

<br>

---
### Bolster 

It may be best to save the milling of the Bolster to last as it 
requires removing the tram bar.

1. tram / 4hblk: Mount and tram block as straight edge for workpiece

    * Mount block along front edge of tooling plate, exposing two rows of holes.
    * Tram align block parallel to X axis

    <br>
2. hd / sp: Mount workpiece  

    * Spacer: 1/8" x 1/2" sacrificial plate against block, flush at left
    * Workpiece: 5/16" Brass Square Bar 360-H02 Extruded
    * Position workpiece against block with 1" exposed left 
      ($\approx$1/4" overhanging end of sacrificial plate)
    * Add hold-downs using 1/2" rear support block (do not use step-blocks) 
      - botZ is facing up.
      - sideC is facing away from operator.
      - endB (raw) is facing to left.

    ![]({{image-dir}}Bolster/pocket0-comp.png)
    Workpiece on table. Arrow always points toward topZ surface.
 
    <br>
2. 3/8em: Square off end of workpiece to establish endB

   Rigid 3/8em required to achieve suitable results.  

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Set Y=0 
    * Retract Y to -50mil from 0
    * Advance Z to 350mil from -15mil
    * Turn on mill
    * Repeat to goal of squared workpiece endB ( $\approx$20mil total depth of cut )
      - Advance X in 5mil steps for $\approx$20mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill
    * Set X=0 
    * Retract X to -15mil from 0
    * Retract Z to -15mil from 350mil

    <br>
2. 3/8em: Add step on Bolster endB

    * Retract Z and change tool.
    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at botZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y for cutter centered, X cut just beyond uncut endB
    * Advance Z to 50mil from -15mil
    * Set X=0 at uncut endB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideC
    * Set Y=0 
    * Retract Y to -50mil from 0
    * X,Y,Z are at -15,-50,-15 mil
    * Advance X to 90mil from -15mil
    * Advance Z to -10mil from -15mil
    * Turn on mill
    * Repeat to goal of Z=60mil total depth of cut
      - Advance Z in 10mil steps for 60mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}Bolster/pocket1-comp.png)
    Step at Bolster endB

    <br>
9.  5/16cs1 (1-flute 82$^{\circ}$): Chamfer on endB

    * Retract Z and change tool.
    * Rotate workpiece 180$^{\circ}$
      - topZ is facing up.
      - endB is facing to left.
      - sideC is facing operator
    * Gross center X Y at exposed end of workpiece
    * Advance Z for tool tip to approach topZ
    * Set Z=0 Gross
    * Retract X well beyond endB (so that tool can be lowered)
    * Advance Z to 150mil from 0
    * Rotate cutting edge towards endB
    * Advance X for cut at endB using ohmmeter
    * Set X=0 
    * Retract X to -15mil
    * Gross adjust Y for cut beyond sideA
    * Set Y=0 
    * Retract Y to -50mil from 0
    * Turn on mill
    * Repeat to goal of chamfer on endB 
      - Advance X in 5mil steps for $\approx$90mil total depth of cut
      - Full Sweep Y: advance to Y=450mil (_SC_), retract to Y=-50mil(_NCC_)  
    * Turn off mill

    ![]({{image-dir}}Bolster/chamfer0-comp.png)
    Chamfer at Bolster endB

    <br>
9.  ss (sabre saw): Chop Bolster 

    ```
    This procedure is a bit rough.  I don't really have a simple way
    to chop other than milling opposing dado's. (painful)
    ```

    * Dismount workpiece
    * Mark $\perp\chi$ at 1" beyond endB with pen
    * Mount in bench vise (?)
    * Chop off Bolster
    * Tidy up the chopped end by hand.

    ![]({{image-dir}}Bolster/pocket2-comp.png)
    Chopped Bolster (orienting arrow removed by the chop)

    <br>
9.  vise & 1/8em : Bolster pad channel 

    * Remove tram plate from table
    * Affix vise, lengthwise Y, squared on table 
    * Mount Bolster in vise
      - endB upwards, just exposing step and chamfer.
      - sideA facing operator (sqared by vise) 
      - topZ facing left, perpendicular to table

    * Gross center X Y at exposed end of workpiece
    * Set Z=0 at endB using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust Y beyond sideC
    * Advance Z to 50mil from -15mil
    * Set Y=0 at sideC using ohmmeter
    * Retract Y to -15mil from 0
    * Gross adjust X beyond topZ 
    * Advance Z to 150mil from 50mil
    * Set X=0 at topZ using ohmmeter
    * Retract X to -50mil from 0
    * Retract Z to -15mil from 150mil
    * Advance X to 450mil from -50
    * Advance Y to 230mil from -15mil
    * Turn on mill
    * Repeat to goal of 90mil deep dado
      - Advance Z in 10mil steps 90mil total depth of cut
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=450mil(_NCC_)  
    * Turn off mill
    * Retract Z to -15mil from 90mil
    * Retract X to -50mil from 450mil
    * Retract Y to -15mil from 230mil

    * Advance Y to 195mil from -15mil
      - _assumes that 1/8em is actually 125mil diameter_
    * Turn on mill
    * Repeat to goal of 90mil deep dado
      - Advance Z in 10mil steps 90mil total depth of cut
      - Full Sweep X: advance to X=450mil (_SC_), retract to X=-50mil(_NCC_)  
    * Turn off mill

    * Measure thickness of finger at sideC (away from operator)
      - goal is 70mil thickness, but 1/8em may not be perfect...
      - if too thick then reset Y to correct and repeat previous milling operation

    ![]({{image-dir}}Bolster/pocket3-comp.png)
    Pad channel in Bolster

<br>

---

<br>

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
