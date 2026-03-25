---
layout: default
title: Rev.5 Guide Key 7 Countersink Procedure
tip: countersink guide key 7, rev 5
date:   2026-03-20 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
  blog: project/su.piston.position/guideKey.7/machining
---
<style>
blue {
  color: lightblue;
}

red {
  color: red;
}

green {
  color: lightgreen;
}
</style>

{% include mathjax.html %}

{% capture image-dir %}
  {{site.url}}/assets/mini/project/su.piston.position/guideKey/
{% endcapture %}

Last update {{ page.date | date: "%d %b %Y" }}.

While developing the _"Rev.5 Guide Key 7 Machining Procedure"_
I came up with this step for milling the screw hole countersink:

<red>This was the proposed countersink procedure:</red>

*   5/16cs (6-flute 60$^{\circ}$): Countersink the screw hole  
    __This step is for the HIF6 1/8-40 BSW imperial screw.__
    * The top diameter of the chamfer must exceed 184mil
      to accomodate the BSW screw.  
      (as measured)

    <br>
    __/This step is an experimental procedure to 
    establish the countersink for the screw. /__

    For $S$=diameter of screw hole, $D$=diameter of cs, $H$=depth of cs, $\theta$=angle of countersink:  

    <p style="text-align: center;">
      $H = \frac{D-S}{2 tan(\frac{\theta}{2})}$
    </p>

    For HIF6: $S$=125mil, $D$=185mil, $\theta$=60$^{\circ}$:  

    <p style="text-align: center;">
      $H = \frac{185-125}{2 tan(\frac{60}{2})} \approx 52mil$
    </p>

    * Retract Z and change tool
    * Advance Z to ohmmeter contact  
      _The tip of cs will be inside the screw hole.  
      The contact will be at the rim of the screw hole.  
      It may help to manually jog tool rotation as Z is advanced.  
      Try to avoid cutting the rim of the screw hole._
    * Set Z=0
    * Retract Z to -15mil from 0
    * Turn on mill
    * Advance Z to 52mil from -15mil 
    * Retract Z to -15mil from 0
    * Turn off mill
    * __*evaluate diameter of resulting countersink*__

<red>End of the proposed countersink procedure:</red>

<br>

But I thought it might be a good idea to try it out before risking damaging
the next guide key. And it's a good thing I did.  Because the countersink
milling is not-so-easy!

What I did was an experiment along the lines of the above procedure:

1. Mount a piece of 1/4" square bar on top of a 1/4" spacer so that
the end of the bar is cantilevered about 3/4" overhang.
   * This is to allow for the upcoming through hole drill to fully
   pass through the bar without damaging the table below.

2. 1/8cd create a divot for drilling centered on the bar end with sufficient
   space for the countersink diameter (185mil goal).

3. 1/8sd drill the screw hole all the way through the bar.

4. 5/16cs 60$^{\circ}$
   * Advance Z to contact rim of hole (ohmmeter)
   * Set Z=0
   * Same speed as drilling (medium) Advance Z to 52mil
     - Here I noticed resistance to advancing Z
   * Retract Z and evaluate size of cs.
     - substantial burr around countersink observed.
     - placing screw in hole, it's head appeared to be 40mil above the
       top surface of the bar (using feeler gauge to measure).
   * Advance Z to 90mil to make up for the 40mil shortfall.
     - again with resistance to advancing Z. did some jogging to get to 90mil.
   * Retract Z and evaluate size of cs.
     - still the screw is at least 10mil above the top surface.

5. Question: Is the brass material bending?
     - large burr at cs rim.
     - some deformation of bar end adjacent to cs
   * Dismounted bar
     - deburred cs rim
     - measured cs rim as 171mil, well short of 185mil goal.
   * Carefully evaluated the screw 
     - screw head is definitely 60$^{\circ}$
     - screw head taper is about 40mil so the 52mil goal should be more
       than enough.
     - but since screw is still 10mil proud of top bar surface the actual
       depth of the countersink is more like 30mil in spite of
       driving Z to 90mil!

6. Yikes!

7. What do the experts say?
   * After quite a bit of searching I did not find a whole lot of
     good advice beyond what I am already doing... except...
   * There is discussion regarding the use of single and multiple
     flute countersinks.  It seems that single flutes can run faster
     but also wear out faster.  Multiple flute, like 6, can produce
     a better finish, but must be run more slowly.
   * Ultimately I did not really find a strong suggestion.

8. So I flipped the bar over and remounted it with no cantilever.  
   It already had the 1/8" hole.

9. 5/16cs 60$^{\circ}$
   * Using the ohmmeter I was able to lower the cs into the hole and
     recenter it. (A new way to find a hole center!)
   * Set Z=0
   * Set speed much lower
   * Slowly advance Z to 52mil with lots of jogging and adding cut oil
     - Again noticed resistance to advancing Z above 30mil or so.
   * Retract Z and evaluate size of cs.
     - substantial burr around countersink observed.
     - placing screw in hole, it's head again appeared to be 40mil above the
       top surface of the bar
   * Removed bar
     - deburred
     - measured cs rim as 170mil!
10. Evaluation and comments
    * BOTH of the above experiments yielded a 170mil cs with grossly
      different Z drive levels.
      - $H = \frac{170-125}{2 tan(\frac{60}{2})} \approx 39mil$
      - 39mil is consistent with observed screw head sitting about 10mil proud.
    * BOTH experiments had resistance to advancing Z beyond modest levels
    * It's as if the cs simply stopped cutting further once the 170mil
      size was reached.
      - with 6 flutes the Z force is distributed around the cutting surface
      - as the cs goes deeper the surface area increases
      - as the surface area increases, more Z force is needed to advance the cut
      - at higher levels of force, the mill itself flexes? --not supported in literature
      - at higher levels of force, the 6-flute-cs begins to 'float'
       on a bearing-like surface?  (Where does the excess Z go?)

    * Literature does not support that free-cutting brass has a problem with
   elasticity.
    * Literature does not suggest freezing brass to maintain cutting.  However
      it does emphasize the notion of continuous flooding with oil during the
      cut.  (I don't have the equipment for such an arrangement on my mill.)

11. Plan for a new experiment: 
    * purchase 1/4cs 60$^{\circ}$ 1-flute countersink
      - evaluate 
      - the notion is that with one flute, the Z-force will be concentrated
        rather than distributed (across 6 flutes) so a deeper cut can be
        achieved.
      - perhaps use 6-flute to finish the chamfer.

---
<br>

The new experiment is much like the old, but using 1/4cs 60$^{\circ}$ 1-flute countersink:

1. Mount a piece of 1/4" square bar on top of a 1/4" spacer so that
the end of the bar is cantilevered about 3/4" overhang.
   * This is to allow for the upcoming through hole drill to fully
   pass through the bar without damaging the table below.

2. 1/8cd create a divot for drilling centered on the bar end with sufficient
   space for the countersink diameter (185mil goal).

3. 1/8sd drill the screw hole all the way through the bar.

4. 1/4cs 60$^{\circ}$ 1-flute
   * Advance Z to contact rim of hole (ohmmeter)
   * Set Z=0
   * Same speed as drilling (medium) Advance Z to 52mil
     - Here I noticed much less resistance to advancing Z
     - let it sit there a few moments prior to retraction.
   * Retract Z and evaluate size of cs.
     - minimal substantial burr around countersink observed.
     - placing screw in hole, it's head appeared to be nearly flush with
       top surface of the bar, about the same as in the guide key.
     - quality of the taper looks good.
   * Advance Z to 55mil attempting complete flush
     - still slightly proud
     - estimate 192mil of cs outer diameter. (hard to measure in situ)
   * Advance Z to 60mil attempting complete flush
     - almost perfect.  
     - the screw head itself is not completely flat due to use.
   * Retracted Z and dismounted bar.
     - cs outer diameter measures 198mil.
     - original guide key measures 182mil cs od.
     - this is about a far as I'd like to take it.
     - very nice fit
   * Success!
     - why?

This experiment performed _much_ better than the previous 6-flute experiment.
But is the difference really the number of flutes?  
I think not.

It occurred to me that the difference in the two setups could be attributed
entirely to having not sufficiently tightened the collet for the 6-flute
countersink.  At the 170mil diameter the force to increase further cutting
was less than the force to push the countersink into the collet.  This
is why both trials in the first experiment stopped at 170mil.
When I mounted the 1-flute countersink
I was careful to tighten the collet completely.

So this experiment is much ado about nothing. Except as a reminder to
steadfastly identify and observe best practices!

I need to confirm the above result by repeating the experiment with the
6-flute, properly tightened in the collet.


