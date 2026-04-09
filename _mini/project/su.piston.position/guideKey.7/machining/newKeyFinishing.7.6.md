---
layout: default
title: Rev.6 Guide Key 7 Finishing Procedure
tip: finishing guide key 7, rev 6
date:   2026-04-07 01:00:00 -0700
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

NewKey Finishing Revision 6:
* Procedure followed to finish brassKey5 subsequent to
    [newKeyMachining 7.6]({{ site.url | append: "/mini/project/su.piston.position/guideKey.7/machining/newKeyMachining.7.6.html" }})

* Produced third newKey:  brassKey6

* Use drawing newKey.5
  - The newKey.5 drawing adds guidepoint for tongue length trim.

<br>
### Tools

| __TOOL__ | __FIXTURE__ | __DESCRIPTION__ |
| ----------- |:----------:| ----------:|
tram | Chuck | Dial Tram Gauge
4hblk | 4" x 10" Mill Tooling Plate | 4 hole block 1/4" x 1-1/2" x 4"
vise | 4" x 10" Mill Tooling Plate | Vise mounted with jaws along X, bolt to rear
hd | 4" x 10" Mill Tooling Plate | hold-down  
3/8em | End Mill Holder | 3/8" end mill
1/4em | End Mill Holder | 1/4" end mill
1/8em | 1/8" collet | 1/8" end mill
1/8sd | 1/8" collet | 1/8" short drill
1/8cd | 1/4" collet | 1/8" center drill
1/4cs | 1/4" collet | 1/4" countersink (1-flute 60$^{\circ}$)
5/16cs | 1/4" collet | 5/16" countersink (6-flute 60$^{\circ}$)
caliper | hand | digital caliper
1/4cant | vise | 1/4" square workpiece with cantilever end and 1/8" hole

## Procedure:

Having produced brassKey6 by machining, this procedure was
followed to finish the part.  The objective here was to 
attempt to size the part for installation in the HIF6 rebuilt carb.
The primay objective is to center the tongue and set its width to 140mil.
These steps are generally beneficial as a basis for future parts.

<br>
`In the following steps:`  
_`SC:`_`Standard Cut`  
_`CC:`_`Climb Cut`  
_`NCC:`_`No Climb Cut, No cut made despite climb direction motion`


{% include figure.html
           img-dir=image-dir
           img-file='brassKey6Finish-comp.png'
           alt='brassKey4 in mill'
           caption='BrassKey6 at Finish. BrassKey6 is mounted in vise on cantilever spacer.'
%}

<br>
Although I'm not yet entirely happy, these images show progressive improvement
in producing brassKeys.

<br>
{% include figure.html
           img-dir=image-dir
           img-file='brassKey246top-comp.png'
           alt='brassKeys 2 4 and 6 top view'
           caption='BrassKeys 2 4 and 6 (rear to front) after Finishing'
%}

<br>
{% include figure.html
           img-dir=image-dir
           img-file='brassKey246side-comp.png'
           alt='brassKeys 2 4 and 6 side view'
           caption='BrassKeys 2 4 and 6 (rear to front) after Finishing'
%}

<br>
1. vise: Mount and tram vise 

    * Mount vise on table with jaws along X-axis, adjustment bolt to rear. 
    * Tram adjust vise parallel to X axis

    <br>
2.  caliper: Measure heel and tongue width  
    Heel width is determined by the original 1/4" workpiece.  Tongue width is determined
    by the Machining process.  The goal tongue width of this procedure is 140mil.

    Ideally gapA = tongueA - sideA = gapC = sideC - tongueC = $250 - 140 \over 2$ = 55mil

    * Measure: heel width sideA to sideC
      - Heel width Measured: <ins>...250.0...</ins> mil
    * Measure: tongue width tongueA to tongueC
      - Tongue width Measured: <ins>...163.5...</ins> mil  

    <br>
3. vise: Mount brassKey  

    * Cant (Cantilever bar) is modified workpiece: 0.25" Brass Square Bar 360-H02 Extruded
    * Cant has one end milled to 200mil thick with 1/8" hole beyond milling to form a step.
    * BrassKey mounts to cant with #4-40 screw/washer/nut on end of cant such that tongue
      becomes a cantilever with the step clearance below it. Note that topZ surface
      is upward.
    * Position cant/brassKey assy in vise at edge of jaws.  This is to allow 
      machining of the tongue without interference from the vise or the cant bar.
    * Note that jaws of vise are holding the brassKey aligned to X-axis, preventing
      any rotation arount the screw. (The screw does not need to be very tight.)
    * Level the assembly and tighten vise.

    <br>
4. 1/8em: Measure tongueA - sideA

    * Retract Z and change tool.
    * Gross center X Y at exposed end of brassKey
    * Set Z=0 at topZ using ohmmeter
    * Retract Z to -15mil from 0
    * Gross adjust X,Y for cutter near center of tongueB, beyond edge.
    * Advance Z to 20mil from -15mil
    * Set X=0 at tongueB using ohmmeter
    * Retract X to -15mil from 0
    * Gross adjust Y beyond sideA
    * Advance X to 300mil from -15mil (make sure tool does not interfere)
    * Advance Y to set Y=0 at sideA using ohmmeter, be particularly careful here.  
      Once Y=0 is set __do not rotate tool__
    * Retract Y to -15mil from 0
    * Retract X to 150mil from 300mil
    * Advance Z to 50mil from 20mil
    * Advance Y, _carefully_, to ohmmeter contact with tongueA
    * Record: Y position at contact with tongueA
      - Position: <ins>...40...</ins> mil  (gapA = sideA - tongueA)
    * Retract Y to -15mil from tongueA

    <br>
5. 1/8em: Measure sideC - tongueC

    * Retract Z to -50mil from 50
    * Retract X to 100mil from 150 (in order to clear the nut)
    * Advance Y beyond sideC from tongueA
    * Advance X to 300mil from 100mil
    * Advance Z to 20mil from -50mil
    * Retract Y to set Y=0 at sideC using ohmmeter, be particularly careful here.  
      Once Y=0 is set __do not rotate tool__
    * Advance Y to +15mil from sideC
    * Retract X to 100mil from 300mil
    * Advance Z to 50mil from 20mil
    * Retract Y, _carefully_, to ohmmeter contact with tongueC
    * Record: Y position at contact with tongueC
      - Position: <ins>...-52...</ins> mil  (gapC = sideC - tongueC)
    * Advance Y to +15mil from tongueC  
      <br>
    * Consider: tongueWidth = heelWidth - gapA + gapC  
      - heelWidth <ins>...250...</ins> - gapA <ins>...40...</ins> + gapC <ins>...-52...</ins> = tongueWidth <ins>...158...</ins> mil
      - But Caliper now says <ins>...160.5...</ins> mil
      - Why different? (<ins>...2.5...</ins> mil)
      - The caliper measurement seems to have variability, perhaps due to hand manipulation.  
        I choose to consider the Sherline as the more reliable measurement...
    * To achive 140mil tongue width (55mil gaps), with centered tongue:
      - Remove 55 - gapA = 55 - gapA <ins>...40...</ins> = <ins>...15...</ins> mil
        from tongueA
      - Remove 55 + gapC = 55 + gapA <ins>...-52...</ins> = <ins>...3...</ins> mil
        from tongueC
      - It is lucky that the goal can be achieved by removing material rather than adding it!

    <br>
6. 1/8em: Remove material to reset tongueC for gapC = -55mil

    * Z is at 50mil
    * X is at 100mil
    * Y is at +15mil wrt sideC
    * Retract X to -15mil from 100mil & verify
    * Advance Z to 150mil from 50mil & verify that em tip is aligned in space below cantilever
    * Turn on mill
    * Retract Y to -55mil from +15mil
    * Advance X slowly to 150mil from -15mil (_SC_), allow to settle
    * Retract X to -15mil from 150mil (_NCC_)
    * Turn off mill


    <br>
7. 1/8em: Remove material to reset tongueA for gapA = 55mil

    * Retract Z to -15mil from 150mil
    * Retract Y behind sideA 
    * Advance X to 300mil from -15mil
    * Advance Z to 20mil from -15mil
    * Advance Y to set Y=0 at sideA using ohmmeter, be particularly careful here.  
    * Retract Y to -15mil from 0
    * Retract X to 100mil from 300mil
    * Advance X to 150mil from 100mil (remove backlash)
    * Advance Z to 150mil from -15mil & verify that em tip is aligned in space below cantilever
    * Advance Y to 35mil from -15mil
    * Turn on mill
    * Repeat to goal of Y=55mil:
      - Advance Y in 5mil steps to goal of 55mil
      - Full Sweep X: retract to X=-50mil (_SC_), advance to X=150mil(_NCC_)  
    * Turn off mill
    * Retract Y to -15mil from 55mil
    * Retract X to -15mil from 150mil
    * Retract Z to -50mil from 150mil


    <br>
8.  caliper: Verify tongue width is 140mil  
    * Measure in situ: tongue width should be 140mil
      - Measured in situ tongue width: <ins>...139.5...</ins> mil
      - Appearance: <ins>...beautiful...</ins>
      - Compute: IS_Measured - 140 : <ins>...-0.5...</ins> mil  
    * Dismount assembly from vice
    * Dismount brassKey from cant
    * Deburr brassKey
    * Measure finished: tongue width should be 140mil
      - Measured finished tongue width: <ins>...139.5...</ins> mil
      - Appearance: <ins>...beautiful...</ins>
      - Error: Finished_Measured - 140 : <ins>...-0.5...</ins> mil  

    <br>

---

<br>

### Finished dimensions, mils:

| __FEATURE__ | __TARGET, mil__ | __ACTUAL__ |
| ----------- |:----------:| ----------:|
tongue width | 140 | ...139.5... 
tip to heel | 520 | ...508...
heel to hole edge | 137.5 | ...172...
tip to hole edge | 257.5 | ...210...
hole diameter | 125 | ...125...
side 1 to hole | 62.5 | ...71...
side 2 to hole | 62.5 | ...58...
side 1 to side 2 | 250 | ...250.5...
key thickness | 100 | ...99.5...

### Notes:

* The finishing process to center and set the tongue width was satisfactory.

* At long last, it's time to try fitting brassKey5 into the HIF6rebuilt
  carburettor.  
  - Hand fit to piston groove feels good, not binding, no play 
  - installing in carb with piston & bell assembled
    - it does not bind the piston throughout its travel
    - brassKey5 prevents most of the piston rotation
    - there is some piston rotation, barely more than 1/2mm, perhaps 0.6mm
  - Remember that brassKey5 tongue is short by 11 to 20 mils and the 
    piston groove itself is worn to a taper.

* All in all brassKey5 is a success.

{% comment %}
[markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

[markdown syntax](https://learn-markdown.github.io/assets/markdown-cheatsheet.pdf)
{% endcomment %}
