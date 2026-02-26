---
layout: default
title: Rev.4 Guide Key 7 Machining Procedure
tip: machining guide key 7, rev 4
date:   2026-02-03 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
  blog: project/su.piston.position/guideKey.7/machining
---
Last update {{ page.date | date: "%d %b %Y" }}.

Version 4: as with V3 but accounts for 1/8em flexture.

* Focus on getting the tongue width correct and the anchor hole
centered on the tongue.

* Use drawing newKey.4
  - The newKey.4 drawing adds guidepoint for 1/4em first-pass at tongue
  - The newKey.3/4 drawing does not account for retracting the shoulders per.se.
         Instead, it removes the shoulders altogether.
         This has implications regarding the tongue length.

<div></div> {% comment %} experimental spacing {% endcomment %}
* The setup is upgraded to add a solid straight edge bar,
mounted on the table plate and tram'd true,
for mounting the workpiece. This seems to significantly improve
rigidity.

## Procedure:

1. 0.25" Brass Square Bar 360-H02 Extruded

2. Brass Square Bar working end facing left (operator pov)

3. 3/8em: Square off end of bar to depth ~ 200thou


    Note: When first attempting V3 I chose to attempt this
          step using 1/8em, in order to avoid tool change.
          The result was a poor quality squaring with poor surface finish.
          The problem seems to be excessive deflection of the 1/8em
          bit with large side loads.  
          I repeated this step, using 3/8em, and got much better results.

    ```
    Added steps 4, 5 and 6 for Rev 4:
      Goal is to reduce 1/8em depth of side cuts to less than 10mil,
      as a finishing step, to avoid tool deviation due to side forces.
   
      See drawing newKey.4
    ```

3. 1/4em: Establish reference point for top side milling
    *     Raise Z and change to 1/4em end mill tool
    *     using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
    *     Y=0 is bar face surface, X=0 is squared bar end
    *     Z=0 is upper surface. Z increases as mill is lowered.

    <br>
    Note: skip fly cut.  No real value and forces cantilever
      once part is flipped over.


    *     Back off X to -10mil, Y to -10mil, Z to -10mil.

    <br>
    ```
    In the following 2 steps to avoid Y backlash:
      Y will ONLY be advanced + direction
      X will return to -10mil before moving pos+
    ```

4. 1/4em: Gross Cut first side of tongue (10mil oversize)
    *  Advance Z to 150mil
    *  Advance Y to   5mil
    *  Turn on mill

    *  Repeat to goal:
       -  Advance X to 235mil, then retract to -10mil
       -  Advance Y incrementally towards goal Y=40mil, Repeating X route.

       <br>
    *  Return X to -10mil
    *  Raise Z to -10mil
    *  Turn off mill

    <br>
5. 1/4em: Gross cut second side of tongue (10mil oversize)
    *  Back off X to -10mil
    *  Raise Z to -10mil
    *  Advance Y from 40mil to 460mil (10mil beyond final tongue edge)
    *  Turn on mill

    *  Repeat to goal:
       -  Lower Z incrementally towards goal Z=150mil, Repeating X route.
       -  Advance X to 235mil, then retract to -10mil
          
    <br>
    *  Retract X to -10mil
    *  Raise Z to -10mil
    *  Turn off mill

    *  Freecut:
       -  Deburr: lower Z -> 0mil X, Y as needed to deburr top edges

    <br>
    ```
End of Rev 4 extra steps
    ```
    <br>
7. 1/8em: Establish reference point for top side milling
    *  Raise Z and change to 1/8em end mill tool
    *  using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
       - Y=0 is rotated flycut surface, X=0 is squared bar end
       - Z=0 is upper surface. Z increases as mill is lowered.

    *  Back off X to -10mil, Y to -10mil, Z to -10mil.
    *  In the following steps
       - Y will ONLY be advanced + direction
       - X will return to -10mil before moving pos+

    <br>
8.  1/8em: Cut first side of tongue
    * Advance Z to 150mil
    * Advance Y to   5mil
    * Turn on mill
    * Repeat to goal:
       -  Advance X to 213mil, then retract to -10mil
       -  Advance Y incrementally towards goal Y=50mil, Repeating X route.

    *  Return X to -10mil
    *  Raise Z to -10mil
    *  Turn off mill

    <br>
9. 1/8cs: Locate screw hole
    *  Raise Z and change to 1/8cs tool
    *  Lower Z and locate Z=0; raise Z to -10mil
    *  Advance Y from 50mil to 187.5mil
    *  Advance X from -10mil to 432.5mil
    *  Turn on mill
    *  Lower Z to 20mil cutting hole center location divot
    *  Raise Z to -10mil
    *  Turn off mill

    <br>
10. 1/8sd: Drill screw hole
    *  Raise Z and change to 1/8sd short drill bit tool
    *  Lower Z and locate Z=0; raise Z to -10mil
    *  Turn on mill
    *  Lower Z to 200mil drilling hole
    *  Raise Z to -10mil
    *  Turn off mill

    <br>
11. 5/16cs: Countersink screw hole
    *  The top diameter of the chamfer must exceed 6mm (237thou)
            to accomodate both BSW and metric screws. (per spec sheets)
       -  Existing metric screw head is more like 5.5mm
    *  Look at the drawing to see how close this comes to the edge.
       -  ... it's really close.
       -  goal: 238mil leaves 6 mil clearance on anchor!
    *  Raise Z and change to 5/16x6flute countersink
    *  Lower Z and locate Z=0; raise Z to -10mil

    *  Repeat to goal of 238mil diameter:
       -  Turn on mill
       -  Lower Z to ???mil to enlarge countersink diameter
       -  Raise Z to -10mil
       -  Turn off mill
       -  measure diameter

    *  Back off X to -10mil

    <br>
12. 1/8em: Gross cut second side of tongue
    *  Raise Z and change to 1/8em end mill tool
    *  Back off X to -10mil, advance to 150mil
    *  Lower Z and locate Z=0; raise Z to -10mil
    *  Back off X to -10mil
    *  Advance Y from 187.5mil to 335mil (10mil beyond 325mil target)
    *  Turn on mill
    *  Repeat to goal:
       -  Lower Z incrementally towards goal Z=150mil, Repeating X route.
       -  Advance X to 213mil, then retract to -10mil
          
    *  Retract X to -10mil
    *  Raise Z to -10mil
    *  Turn off mill

    <br>
13. Caliper: Verify tongue is 160mil wide (gross).
    *  Expected thickness is 160mil, desired is 150mil
    *  Compute delT, the measured - 150mil goal.

    <br>
14. 1/8em: Finish cut second side of tongue
    *  Advance Y to 345mil to prepare for retraction
    *  Lower Z to 150mil
    *  Retract Y ~10mil to touch with ohmmeter (backlash reversal)
       - Reset Y=0
       - Y has now lost original alignment but X is still aligned.

    *  Goal here is to remove delT in Y for 150mil final, repeat to goal:
       - Lower Z to 150mil
       - Retract Y incrementally towards 150mil tongue width goal
       - Turn on mill
       - Advance X to 213mil, then retract to -10mil
       - Turn off mill
       - Raise Z to -10mil
       - Caliper measure tongue width and compute new delT

    *  Advance Y to +10mil
    *  Raise Z to -10mil

    <br>
15. 1/8em: Top side dado for cut off.
    *  Cut dado on anchor heel:
       -  Advance X to 695mil 
       -  Lower Z to 10mil
       -  Retract Y to -400mil
       -  Lower Z to 20mil
       -  Advance Y to +10mil
       -  Raise Z to -10mil
       -  Retract X to -10mil

    <br>
16. Finalize tongue length, this step allows for subsequent trimming?

    Note: skip this step until tongue length is fully determined:

    >  It's probably best to skip this step for the first part.
    >  Fitting and measuring first should yield a better
    >  idea of what the tongue length should be.
    >  It may be better to make a fixture solely for trimming
    >  the tongue length...
    >
    >  ...these instructions are subject to editing later:
    >  At this stage the tongue length is 150mil

    *  The nominal tongue length is 80mil, subject to fitting
       -  cut rabbet on tongue end:
       -  Advance X to 70mil 
       -  Lower Z to 10mil
       -  Retract Y to -400mil
       -  Lower Z to 20mil
       -  Advance Y to +10mil
       -  Raise Z to -10mil
       -  Retract X to -10mil

    <br>
17. Top surface is done.
    *  Clean up as necessary.

18. Dismount bar, rotate 180deg, remount facing left.

19. 3/8em: Rabbet part end to expose tongue tip

    The rabbet cut in this step will be removed on the subsequent fly cut

    * Raise tool perhaps 50mil above part top surface at 250mil
    * Gross align Y at part center, X above uncut surface 
    * Lower tool to ohmmeter touch top surface.
    * Set Z=0, Raise to Z=-10mil

    * Gross align Y for tool on operator side of part
    * Gross align X for tool to just intersect tongue tip

    <br>Goal here is to expose tongue tip for X alignment:

    - turn on mill
      + Incrementally lower Z to goal of ~50mil
      + Half Sweep Y: (retract to Y=650mil or advance to Y=-10mil)
      + Repeat until tongue tip is just exposed
    - turn off mill

    * Raise Z to -10mil  

    <br>

20. 3/8em: Fly cut to reduce part to 150mil thickness.

    Also leaves room for 1/8" anchor cutoff dado

    <br>Gross align Y at part center
    *  Retract X such that tool edge is perhaps 50mil beyond tongue tip
    *  Advance X such that tool edge is perhaps 10mil beyond tongue tip
    *  Set X=0, Retract to X=-10

    <br>Goal here is to incrementally remove 100mil for 150mil final height:
    *  turn on mill
       - Incrementally lower Z to goal of 100mil
       - Full Sweep X: advance to X=1100mil, retract to X=-10mil
    *  turn off mill
    * Raise Z to -10mil

    <br>
21. 1/8em: Dado between anchor and tongue

    Goal is 20mil deep dado

    *  Gross center Y X
    *  Lower Z to ohmmeter touch
    *  set Z=0, raise to Z=-10mil
    *  Retract X for tool beyond tongue tip
    *  Lower Z to 50mil
    *  Advance X to ohmmeter touch
    *  set X=0, retract to X=-10
    *  Raise Z to -10mil
    *  Gross align Y for tool on operator side of part, set Y=0
    *  Advance X to 255mil
    *  turn on mill
    *  Lower Z to 10mil
    *  Retract Y to ~-440mil
    *  Lower Z to 20mil
    *  Advance Y to +10mil
    *  turn off mill
    *  Raise Z to -10mil

    <br>
22. 1/8cs: chamfer Dado at tongue edge

    Goal is nearly full chamfer of edge

    *  Raise Z and change tool.
    *  Retract X to -10mil
    *  Advance X to 192mil
    *  Retract Y to -100mil
       -  -> tip of cs is now over tongue, 0.5mil offset from dado edge
    *  Lower Z to ohmmeter contact
    *  set Z=0, raise to -10mil
    *  Advance Y to +10mil

    <br>Goal is to create 18mil chamfer 
    *  turn on mill
       -  Incrementally lower Z to goal of 18mil
       -  Half Sweep Y: (retract to Y=650mil or advance to Y=-10mil)
    *  turn off mill
    *  Raise Z to -10mil
    *  Retract X to -10mil
    *  Advance Y to +10mil

    <br>
23. 1/8em: Dado between anchor and tongue

    Goal is 20mil deep dado, then cut off part

    *  Raise Z and change tool.
    *  Retract Y to -100mil
    *  Advance X to 695mil
    *  Lower Z to ohmmeter touch
    *  set Z=0, raise to Z=-10mil
    *  Advance Y to +10mil

    *  turn on mill
    *  Lower Z to 10mil
    *  Retract Y to ~-440mil
    *  Lower Z to 20mil
    *  Advance Y to +10mil
       - ...Continue cutting dado deeper, cutoff occurs at Z=130mil
    *  turn off mill
    *  Raise Z to -10mil

    <br>
24. Done. Miller time.

25. Finishing and trimming tongue to length is left as a future exercise.

