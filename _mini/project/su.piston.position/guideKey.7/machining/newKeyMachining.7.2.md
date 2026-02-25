---
layout: default
title: Rev.2 Guide Key 7 Machining Procedure
tip: machining guide key 7, rev 2
date:   2026-01-11 01:00:00 -0700
binder:
  tome:  project  # a single word common to all levels in the work 
  level: blog # identifies presentation level of this file.
  topics: [ ] # applies to book level
  themes: [ guideKey.7 ] # applies to chapter level
  blog: project/su.piston.position/guideKey.7/machining
---
Last update {{ page.date | date: "%d %b %Y" }}.

Version 2: avoid having to machine thin material.
   Use drawing newKey.2

0. 0.25" Brass Square Bar 360-H02 Extruded

1. 3/8fc: Fly cut flatten surface ~0.75" at end of bar. (5thou)

2. 1/8cs: Center hole for larger hole:
   * 1/8d: Drill centered 0.125" (1/8") dia hole ~0.5" from bar end.
   * depth no more than 0.20" (0.18")
   * ==> consider a different size drill bit (smaller)

3. 1/8em: Cut 1st lateral pocket 0.125" wide 0.020" deep
   * inner edge 0.115 from hole center,
   * center 0.115 + 0.125/2 = 0.1775 from hole center

4. 1/8em: Advance tool 0.185" towards bar end.
   * center 0.115 + 0.125/2 + 0.185" = 0.3625 from hole center,
   * center 0.30 + 0.125/2  = 0.3625 from hole center,
   * Square off bar end 0.060 from outer edge of lateral pocket.
   * must exceed 0.100 (0.12) depth but must not extend full 0.25" of stock

5. 1/8em: Advance tool (@end) 0.5 + 0.125 = 0.625" towards heel.
   * Cut 2nd lateral pocket 0.125" wide 0.030" deep,
   * edge 0.20" from hole center = 0.315" from 1st pocket.

6. 5/16cs: Chamfer outer edge of 1st pocket

   Note: for steps 7 and 8
   - Key slot in piston is 0.140", standard key tongue is 0.138"
   - Plan would be to shoot for 0.140" and then lap for 0.138"
   - This is a super tight tolerance for my present skill level.
   - How to ensure foremost that tongue is centered?

     1. Rotate on side, insert 1/8" (0.125) pin in hole
     1. Adjust Z to find hole edge (continuity meter)
     1. Raise Z (140 - 125)/2 = 7.5mil
        + 7mil -> 139mil final
        + 8mil -> 141mil final
        +  ==> Revealed that hole is not square to bar!
           Is this due to the way it's clamped?

7. 1/8em: Rotate 90deg and cut shoulder to depth ~0.050".
   *      0.007 above edge of pin; 0.080 from end

8. 1/8em: Flip and Rotate 180deg and cut other shoulder to depth ~0.050".
   *      0.007 above edge of pin; 0.080 from end
   * ==> result is tongue width 133mil rather than 138mil.
       (procedure needs improvement)

9. 3/8fc: Turn lateral pockets facing downward.
   * Fly cut surface ~0.75" at end of bar. Reduce key to 0.10" thickness.  
   * ==> difficult to gauge thickness.
       stack of feeler gauges 0.101" doesn't account for step 1 fly cut.

10. 5/16cs: Chamfer hole to 0.09" dia. opening; check head of screw fit.
   * ==> added wood spacer to workpiece so that countersink does not cut table.
         - not as solid as hoped.
   * ==> difficult to locate hole center
         - difficult to gauge chamfer depth.
         - cut paper strip width of screw head as comparison gauge.
         - then raise tool and direct check chamfer with screw head
   * ==> consider a different countersink 

11. 1/8em: Butt tool at end.  advance from end to 0.5 + 0.125 = 0.625"
    * Cut 3rd lateral pocket 0.125" wide 0.020" deep
    * Key is now held on by tab 0.06" thick

12. 1/8em: Continue deepening 3rd lateral pocket; break off key.

<br>

---
<br>
## Notes post fabrication of first key.
TL;DR  **unusable**.

* Screw head has a different angle than the countersink which is 82deg.
  - this suggests that the screw is actually 60deg.
* Actual key tongue width measures ~133thou, 5 thou too thin.
* Key anchor width 252thou(good). thickness 100thou (dead on)
* Chamfer slightly off center of screw hole.
* Key shoulders uneven, 81 and 84 thou, (target was 80 - not too bad)
  - extend to interfere with piston circumference
  - (is this error the hole or chamfer location?)

Summary:

The major errors are
 1. tongue is too narrow by 5 thou (a lot)
 2. anchor locates shoulders too close to piston
    - target 220thou, visual ~225.
 3. screw hole and countersink misaligned and offset

