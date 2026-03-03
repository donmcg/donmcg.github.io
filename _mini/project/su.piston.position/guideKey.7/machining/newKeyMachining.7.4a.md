---
layout: default
title: Rev.4a Guide Key 7 Machining Procedure
tip: machining guide key 7, rev 4a
date:   2026-03-01 01:00:00 -0700
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

Revision 4a: same as R.4 but adds __clarification__, __*edits*__ and __/comments/__
made when exercising the Rev.4 procedure. 

Revision 4a: as with R.3 but accounts for 1/8em flexture.

* Focus on getting the tongue width correct and the anchor hole
centered on the tongue.

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
    *     Y=0 is bar face surface __, facing away from operator__, X=0 is squared bar end
    *     Z=0 is upper surface. Z increases as mill is lowered.

    <br>
    Note: skip fly cut.  No real value and forces cantilever
      once part is flipped over.


    *     Back off X to __*-15mil*__, Y to __*-15mil*__, Z to __*-15mil*__.

    <br>
    ```
    In the following 2 steps to avoid Y backlash:
      Y will ONLY be advanced + direction
      X will return to __*-15mil*__ before moving pos+
    ```

4. 1/4em: Gross Cut first side of tongue (10mil oversize)
    *  __*Lower*__ Z to 150mil
    *  Advance Y to   5mil
    *  Turn on mill

    *  Repeat to goal:
       -  Advance X to 235mil, then retract to __*-15mil*__
       -  Advance Y incrementally __, by 5mil each,__ towards goal Y=40mil, Repeating X route.

       <br>
    *  Return X to __*-15mil*__
    *  Raise Z to __*-15mil*__ __from 150mil__
    *  Turn off mill

    <br>
5. 1/4em: Gross cut second side of tongue (10mil oversize)
    *  Back off X to __*-50mil*__
    *  Raise Z to __*-15mil*__
    *  Advance Y from 40mil to 460mil (10mil beyond final tongue edge)
    *  Turn on mill

    *  Repeat to goal:
       -  Lower Z incrementally__, 15mil per,__ towards goal Z=150mil, Repeating X route.
       -  Advance X to 235mil, then retract to __*-50mil*__
          
    <br>
    *  __*Raise Z to __*-15mil*__*__
    *  __*Advance X to __*-15mil*__*__
    *  Turn off mill

    *  Freecut:
       -  Deburr: lower Z -> 0mil X, Y as needed __/not needed/__ to deburr top edges
       -  __Measure: tongue should be 190mil__
       +  __*/-> measured 180mil, looks good in appearance/*__ 

    <br>
    ```
End of Rev 4 extra steps
    ```
    <br>
7. 1/8em: Establish reference point for top side milling
    *  Raise Z and change to 1/8em end mill tool
    *  using ohmmeter establish X=0 and Y=0 and Z=0, accounting for backlash
       - Y=0 is __*surface away from operator*__, X=0 is squared bar end
       - Z=0 is upper surface. Z increases as mill is lowered.

    *  Back off X to __*-15mil*__, Y to __*-15mil*__, Z to __*-15mil*__.
    *  In the following steps
       - Y will ONLY be advanced + direction
       - X will return to __*-15mil*__ before moving pos+

    <br>
8.  1/8em: Cut first side of tongue
    * __*Lower*__ Z to 150mil
    * Advance Y to __*35mil*__
    * Turn on mill
    * Repeat to goal __Y = 45mil__:
       -  Advance X to 213mil, then retract to __*-15mil*__
       -  Advance Y incrementally __, in 5mil increments,__ towards goal Y=__*40mil* (this leaves 5mil excess)__, Repeating X route.
       -  __(final tongue goal: 150 + 5 + 5 = 160)__

    *  __Y is at 45mil__
    *  Return X to __*-15mil*__
    *  Raise Z to __*-15mil*__ __from 150mil__
    *  Turn off mill

    <br>
9. 1/8cs __, 1/8collet__: Locate screw hole

    __/ At this point the hold down blocks ran into the body of the
     mill so the countersink did not reach the material.  So I switched
     to using the chuck... which was a mistake.  The chuck has rather
     high TIR and is not intended for side-loads.  A better solution
     is to change the hold down block arrangement, up front in step 2, so that there is
     clearance for the mill.  
     The step that follows is basically correct, but should be performed
     using the collet rather than the chuck. /__

    *  Raise Z and change to 1/8cs tool
    *  Advance Y from __*45mil*__ to 187.5mil
    *  Advance X from __*-15mil*__ to 432.5mil
    *  __*Lower Z and locate Z=0; raise Z to -15mil*__
    *  Turn on mill
    *  Lower Z to 20mil cutting hole center location divot
    *  Raise Z to __*-15mil*__
    *  Turn off mill

    <br>
10. 1/8sd __, 1/8collet__: Drill screw hole
    *  Raise Z and change to 1/8sd short drill bit tool
    *  Lower Z and locate Z=0; raise Z to __*-15mil*__
    *  __Add cutting oil__
    *  Turn on mill
    *  Lower Z to 200mil drilling hole
    *  Raise Z to __*-15mil*__
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

    <br>
    __/ What follows, in this step, is not possible as the 6-flute countersink does not
      have a sharp tip and cannot be used to establish Z=0.
     What I actually did was to simply eyeball the diameter of the 
      countersink hole.
    /__

    *  ~~Lower Z and locate Z=0; raise Z to __*-15mil*__~~

    *  __*Turn on mill*__

    *  Repeat to goal of 238mil diameter:
       -  ~~Lower Z to ???mil to enlarge countersink diameter~~
       -  __*Lower Z to to enlarge countersink diameter to visual size based on drawing*__
       -  __*evaluate diameter against drawing (difficult)*__

    <br>
    *  __*Raise Z to -15mil*__
    *  __*Turn off mill*__
    *  Back off X to __*-15mil* from 432.5mil__

    <br>
     __/ 6-flute 82$^{\circ}$ countersink still leaves ugly finish with excess burrs. /__

    <br>
12. 1/8em: Gross cut second side of tongue
    *  Raise Z and change to 1/8em end mill tool __with collet__
    *  Back off X to __*-15mil*__, advance to 150mil
    *  Lower Z and locate Z=0; raise Z to __*-15mil*__
    *  Back off X to __*-15mil*__
    *  Advance Y from 187.5mil to __*330mil*__ (__*5mil*__ beyond 325mil target)  
       __This leaves 5mil extra as in step 8.  Goal: 160mil unfinished tongue width.__
    *  Turn on mill
    *  Repeat to goal:
       -  Lower Z __15mil__ incrementally towards goal Z=150mil, Repeating X route.
       -  Advance X to 213mil, then retract to __*-15mil*__
          
    *  Retract X to __*-15mil*__
    *  Raise Z to __*-100mil*__
    *  Turn off mill
  

    <br>
13. Caliper: Verify tongue is 160mil wide (gross).
    *  Expected __unfinished__ thickness is 160mil, desired __finished__ is 150mil  
    __/ Measured unfinished tongue width as 162mil. Goal was 160mil.  Not bad! /__
    *  Compute delT, the measured - 150mil goal.  
    __/ delT = 162 - 150 = 12mil /__

    <br>
14. 1/8em: Finish cut second side of tongue
    *  ~~Advance Y to 345mil to prepare for retraction~~
    *  ~~Lower Z to 150mil~~
    *  ~~Retract Y ~10mil to touch with ohmmeter (backlash reversal)~~
       - ~~Reset Y=0~~
       - ~~Y has now lost original alignment but X is still aligned.~~

    <br>
    *  __/ Y is at 325mil from previous step /__
    *  Goal here is to remove __*delT/2*__ in Y for __*155mil*__ final, repeat to goal:
       - Lower Z to 150mil __from -100mil__
       - ~~Retract Y incrementally towards 150mil tongue width goal~~
       - Turn on mill
       - Advance X to __*254mil*__, then retract to __*-15mil*__
       - Turn off mill
       - Raise Z to __*-100mil*__ __from 150mil__
       - Caliper measure tongue width and compute new delT  
       __/ Measured resulting tongue width as 156mil. Goal here was 155mil. /__

    *  ~~Advance Y to +10mil~~
    *  Raise Z to __*-15mil*__  

    <br>
14. __*1/8em: Finish cut first side of tongue* ( this is a new step  )__  

    *  __Goal here is to remove 5mil (in two passes) in Y for 150mil final:__
       - __Retract Y to 45mil from 325mil__
       - __Lower Z to 150mil from -15mil__
       - __Advance X to 254mil, then retract to -15mil__
       - __Raise Z to -15mil from 150mil__
       - __Advance Y to 50mil from 45mil__
       - __Lower Z to 150mil from -15mil__
       - __Advance X to 254mil, then retract to -15mil__
       - __Retract Y to -25mil from 50mil__
       - __Raise Z to -100mil from 150mil__
       - __Caliper measure tongue width and compute new delT__  
       __/ Measured resulting tongue width as 150.5mil. Goal here was 150mil. /__

    <br>
15. 1/8em: Top side dado for cut off.
    *  Cut dado on anchor heel:
       -  Advance X to 695mil 
       -  Lower Z to 10mil
       -  Retract Y to __*400mil*__
       -  Lower Z to 20mil
       -  Advance Y to __*-15mil*__
       -  Raise Z to __*-15mil*__
       -  Retract X to __*-15mil*__

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
       -  Raise Z to __*-15mil*__
       -  Retract X to __*-15mil*__

    <br>
17. Top surface is done.
    *  Clean up as necessary.
    *  __3/8em: fly cut top surface to deburr__
 
    <br>
18. Dismount bar, rotate 180deg, remount facing left __in the same direction__.

19. 3/8em: Rabbet part end to expose tongue tip

    The rabbet cut in this step will be removed on the subsequent fly cut

    * Raise tool perhaps 50mil above part top surface at 250mil
    * Gross align Y at part center, X above uncut surface 
    * Lower tool to ohmmeter touch top surface.
    * Set Z=0, Raise to Z=__*-15mil*__

    * Gross align Y for tool on operator side of part
    * Gross align X for tool to just intersect tongue tip

    <br>Goal here is to expose tongue tip for X alignment:

    - turn on mill
      + Incrementally lower Z to goal of __*~60mil*_
      + Half Sweep Y: (retract to Y=650mil or advance to Y=__*-15mil*__)
      + Repeat until tongue tip is just exposed
    - turn off mill

    * Raise Z to __*-15mil*__  

    <br>

20. 3/8em: Fly cut to reduce __remaining__ part to __*100mil*__ __final__ thickness.

    Also leaves room for 1/8" anchor cutoff dado

    <br>Gross align Y at part center
    *  Retract X such that tool edge is perhaps 50mil beyond tongue tip
    *  Advance X such that tool edge is perhaps 10mil beyond tongue tip
    *  Set X=0, Retract to X=__*-15mil*__

    <br>Goal here is to incrementally remove _a total of__ __*150mil*__ for __*100mil*__ final __*thickness*__ __of key__:
    *  __/ Z is at -15mil from previous step /__
    *  turn on mill
       - Incrementally lower Z__, in 10mil increments__ to goal of __*150mil*__
       - Full Sweep X: advance to X=__*700mil*__, retract to X=__*-15mil*__
    *  turn off mill
    * Raise Z to __*-15mil*__

    <br>
    *  __Free align X and sweep Y to Z depth of 95mil in order to square off
    rounded corners left by fly cut adjacent to dado.__

    <br>
21. 1/8em: Dado between anchor and tongue

    Goal is 20mil deep dado

    *  Gross center Y X
    *  Lower Z to ohmmeter touch
    *  set Z=0, raise to Z=__*-15mil*__
    *  Retract X for tool beyond tongue tip
    *  Lower Z to 50mil
    *  Advance X to ohmmeter touch
    *  set X=0  ~~, retract to X=-10mil~~
    *  __advance to X=400mil__
    *  Gross align Y for tool __*opposite*__ operator side
    of part __with clearance__, set Y=0
    *  __Retract Y to -15mil__
    *  Raise Z to __*-15mil*__
    *  Advance X to 255mil __from 400mil__
    *  turn on mill
    *  Lower Z to 10mil
    *  __*Advance*__ Y to __*+440mil*__
    *  Lower Z to 20mil
    *  __*Retract*__ Y to __*-15mil*__
    *  turn off mill
    *  Raise Z to __*-15mil*__

    <br>
22. 1/8cs: chamfer Dado at tongue edge

    Goal is nearly full chamfer of edge

    __/ Several problems with this step.  Here, again, I incorrectly used the chuck
    for clearance.  But the approach here puts side loads on the chuck
    which are inappropriate.  Fix is to improve the holddown clearance
    and to use the collet here.  Also the chuck has high TIR which led to 
    poor accuracy here.  Finally this step was written assuming the
    6-flute countersink bit has a sharp tip, which the 1-flute does but 
    the 6-flute doesn't.  /__

    __/ This step needs to be rewritten for next revision /__

    *  Raise Z and change tool.
    *  Retract X to __*-15mil*__ __from 255mil__
    *  Advance X to 192mil __/eyeball was 218mil using chuck/__
    *  Retract Y to -100mil __from -15mil__
       -  -> __/non-existent/__ tip of cs is now over tongue, 0.5mil offset from dado edge
    *  __*Visually confirm position and correct if needed*__
    *  __*Retract X to 100mil from 192mil*__
    *  __Advance Y to +150mil__
    *  Lower Z to ohmmeter contact
    *  set Z=0, raise to __*-15mil*__
    *  ~~Advance Y to +10mil~~
    *  __Retract Y to -10mil from 150mil__
    *  __Advance X to ~~192mil~~ 218mil from 100mil__

    <br>Goal is to create 18mil chamfer 
    *  turn on mill
       -  Incrementally lower Z to goal of 18mil __in 5mil steps__
       -  Half Sweep Y: (retract to Y=650mil or advance to Y=__*-15mil*__)
    *  turn off mill
    *  Raise Z to __*-15mil*__
    *  Retract X to __*-15mil*__ __from 218mil__
    *  Advance Y to +10mil

    <br>
23. 1/8em: Dado between anchor and tongue

    Goal is 20mil deep dado, then cut off part

    __/ Yet another step where I incorrectly used the chuck. Use collet instead. /__

    *  Raise Z and change tool.
    *  Retract Y to -100mil
    *  Advance X to 695mil
    *  Lower Z to ohmmeter touch
    *  set Z=0, raise to Z=__*-15mil*__
    *  Advance Y to +10mil

    *  __Clamp two-hole wood block using hex bolts across key as a hold down
    for final cutoff.__

    *  turn on mill
    *  Lower Z to 10mil
    *  Retract Y to ~-440mil
    *  Lower Z to 20mil
    *  Advance Y to +10mil
       - ...Continue cutting dado deeper, cutoff occurs at Z=130mil
    *  turn off mill
    *  Raise Z to __*-15mil*__

    <br>
25. __Finishing and trimming tongue to length is left as a future exercise.__

24. Done. Miller time.


<br>

---

<br>

### Final dimensions, mils:

| __FEATURE__ | __TARGET__ | __ACTUAL__ |
| ----------- |:----------:| ----------:|
tongue width | 150 | 151.5 
tip to heel | 570 | 573
heel to hole edge | 137.5 | 148.5
tip to hole edge | 307.5 | 307
hole diameter | 125 | 119
side 1 to hole | 62.5 | 65.5
side 2 to hole | 62.5 | 65
side 1 to side 2 | 250 | 253 __(raw barstock)__
key thickness | 100 | 148 __(oops!)__


The major error was that the incorrectly written instruction led to a key
thickness of 148mil rather thatn 100mil.  This rendered the guide key unusable.
I elected not to attempt rework as there is no obvious way to hold the
finished key in position for such a major operation.  Better to do it
better next time!

The hole appears to be well centered. This was a major objective of this revision
of the procedure.

Other, less significant error was smaller than expected hole diameter
which was a bit tight for the screw to fit.  This is unexpected in that
the high TIR of the chuck should have led to a larger hole??  Perhaps the
pilot hold did a really good job and the bit is actually undersized?

The extra long heel was purely due to being conservative and leaving some extra.

All in all these dimensions are pretty good for my second attempt! :-)

Finally, it was found that the tongue seems to fit into the piston groove
just fine as it is at 151.5mil. I expected it not to fit without some polishing.

