---
id: 223
title: Improving lift on IRIS+ with other propellers
date: 2014-10-10T15:44:15+00:00
author: Christian Elsen
layout: post
permalink: /2014/10/10/improving-lift-on-iris-with-other-propellers/
redirect_from: 
  - /2014/10/10/improving-lift-on-iris-with-other-propellers/amp/
image: /content/uploads/2014/10/counter-clockwise-672x372.jpg
thumbnail: /content/uploads/2014/10/counter-clockwise-150x150.jpg
categories:
  - 3DR IRIS
  - Power and Motors
tags:
  - fix
  - hover
  - propeller
---
The all new IRIS+ comes with an upgraded motor as well as propellers versus the previous IRIS. While the new 920 kV motor along with the 5100 mAh 3S Lipo provides added lift of IRIS+ over the 850 kV motor of IRIS, this benefit is actually mitigated by the now shorter 9.5&#215;4.5&#8243; propellers. This means that while IRIS+ features a longer flight time than IRIS, the hover throttle (percent of throttle required to hover) is pretty much the same.

A loiter test flight with IRIS and gimbal and the new IRIS+ 5100 mAh battery shows a flight time of roughly 12 minutes and a hover throttle between 65% and 75% (See Figure 1).

<div id="attachment_225" style="width: 1376px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/iris_5100mah.png" rel="attachment wp-att-225"><img src="/content/uploads/2014/10/iris_5100mah.png" alt="Figure 1: Loiter test with IRIS on 5100 mAh battery" width="1366" height="318" class="size-full wp-image-225" srcset="/content/uploads/2014/10/iris_5100mah.png 1366w, /content/uploads/2014/10/iris_5100mah-300x69.png 300w, /content/uploads/2014/10/iris_5100mah-1024x238.png 1024w" sizes="(max-width: 1366px) 100vw, 1366px" /></a>

  <p class="wp-caption-text">
    Figure 1: Loiter test with IRIS on 5100 mAh battery
  </p>
</div>

The same loiter test flight with IRIS+ and gimbal shows a flight time of roughly 15 minutes but a very similar hover throttle to IRIS, at around 65% to 75% (See Figure 2).

<div id="attachment_226" style="width: 1376px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/iris_5100mah1.png" rel="attachment wp-att-226"><img src="/content/uploads/2014/10/iris_5100mah1.png" alt="Figure 2: Loiter test with IRIS+ on 5100 mAh battery" width="1366" height="318" class="size-full wp-image-226" srcset="/content/uploads/2014/10/iris_5100mah1.png 1366w, /content/uploads/2014/10/iris_5100mah1-300x69.png 300w, /content/uploads/2014/10/iris_5100mah1-1024x238.png 1024w" sizes="(max-width: 1366px) 100vw, 1366px" /></a>

  <p class="wp-caption-text">
    Figure 2: Loiter test with IRIS+ on 5100 mAh battery
  </p>
</div>

This means that the flight time of IRIS did increase, but the lift performance did not. With the heavier setup of IRIS+ and gimbal, you are still at the verge of 70% hover throttle making your IRIS+ a “very underpowered copter” according to <a href="http://ardupilot.org/copter/docs/ac_throttlemid.html" target="_blank" rel="nofollow">http://copter.ardupilot.com/wiki/ac_throttlemid/</a>).

If you ask yourself how this might happen with the new motors delivering higher kVs, look at the new self-tightening propellers that came with IRIS+. While IRIS came with APC 10&#215;4.7&#8243; SlowFly propellers, while IRIS+ features 9.5&#215;4.5&#8243; self-tightening propellers. These smaller length propellers basically reverse the benefits of the higher kV motors when it comes to lift.

The reason for the improved flight time can quickly be found by looking at the Ampere drawn during the flight. IRIS with the 850 kV motors draws more current during a hover test (See Figure 3). It is around 17-18 A.

<div id="attachment_290" style="width: 615px" class="wp-caption aligncenter">
  <a href="https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/iris_5100mah_amps/"><img class="wp-image-290 size-large" src="/content/uploads/2014/10/IRIS_5100mAh_Amps-1024x238.png" alt="Figure 3: Current drawn during flight with IRIS on 5100 mAh battery" width="605" height="140" srcset="/content/uploads/2014/10/IRIS_5100mAh_Amps-1024x238.png 1024w, /content/uploads/2014/10/IRIS_5100mAh_Amps-300x69.png 300w, /content/uploads/2014/10/IRIS_5100mAh_Amps-100x23.png 100w, /content/uploads/2014/10/IRIS_5100mAh_Amps-150x34.png 150w, /content/uploads/2014/10/IRIS_5100mAh_Amps-200x46.png 200w, /content/uploads/2014/10/IRIS_5100mAh_Amps-450x104.png 450w, /content/uploads/2014/10/IRIS_5100mAh_Amps-600x139.png 600w, /content/uploads/2014/10/IRIS_5100mAh_Amps-900x209.png 900w, /content/uploads/2014/10/IRIS_5100mAh_Amps.png 1366w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 3: Current drawn during flight with IRIS on 5100 mAh battery
  </p>
</div>

During the same kind of hover test, IRIS+ with the new 920 kV Tiger motors only consumes about 15-16 A.

<div id="attachment_291" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/IRIS-_5100mAh_Amps.png"><img class="wp-image-291 size-large" src="/content/uploads/2014/10/IRIS-_5100mAh_Amps-1024x238.png" alt="Figure 4: Current drawn during flight with IRIS+ on 5100 mAh battery" width="605" height="140" srcset="/content/uploads/2014/10/IRIS-_5100mAh_Amps-1024x238.png 1024w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-300x69.png 300w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-100x23.png 100w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-150x34.png 150w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-200x46.png 200w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-450x104.png 450w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-600x139.png 600w, /content/uploads/2014/10/IRIS-_5100mAh_Amps-900x209.png 900w, /content/uploads/2014/10/IRIS-_5100mAh_Amps.png 1366w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 4: Current drawn during flight with IRIS+ on 5100 mAh battery
  </p>
</div>

### How to improve lift performance

Using the data for the new IRIS+ propeller in <a href="http://www.ecalc.ch/xcoptercalc.php" target="_blank">xcopterCalc</a> confirms the measured hover throttle to be just barely under 70%. But let&#8217;s try to use <a href="http://www.ecalc.ch/xcoptercalc.php" target="_blank">xcopterCalc</a> and calculate what the hover throttle would be if we mount the old 10&#215;4.7&#8243; propellers from IRIS on IRIS+. And indeed the expected hover throttle will reduce to about 57%, giving us much better lift performance.

In this post I will therefore show you how to improve the lift performance of IRIS+ by using 10&#215;4.7&#8243; SlowFly propellers.

### Required materials and tools

The following material and tools are required:

  * Either the APC Propellers 10X47 Push-Pull Set propellers that came with IRIS, or <a href="http://www.getfpv.com/propellers/hqprop-10x4-7-cw-propeller-slow-flyer-2-blade-2-pack.html" target="_blank">HQProp 10&#215;4.7 CW Propeller Slow Flyer &#8211; 2 Blade (2 pack)</a> and <a href="http://www.getfpv.com/propellers/hqprop-10x4-7-ccw-propeller-slow-flyer-2-blade-2-pack.html" target="_blank">HQProp 10&#215;4.7 CCW Propeller Slow Flyer &#8211; 2 Blade (2 pack)</a>, which are composite propellers featuring a mix of nylon/glass fiber, thus being more rigid and flexing less.

    And the HQProp propellers being black will make the updated IRIS+ look almost like the original IRIS+.
  * <a href="http://amzn.to/2eFdyOc" target="_blank">4 X DJI Phantom Prop Aluminum Alloy Replacement Nuts CW CCW Thread w/ Wrench</a>

### How-to assemble

IRIS+ comes with self-tightening spin-on/off propellers, where the nut is part of the propeller. Also the motor mount shafts &#8211; the part that takes on the propeller &#8211; is either left or right threaded depending on the direction the motor spins. And last but not least the motor mount shaft on IRIS has a diameter of 5 mm, while the motor mount shaft on IRIS+ has a diameter of 6 mm. All this means that we cannot use the same nuts as we did on IRIS for mounting propellers on IRIS+. Here the <a href="http://amzn.to/2eFdyOc" target="_blank">DJI Phantom Prop Aluminum Alloy Replacement Nuts</a> come to the rescue. They allow us to mount almost any propeller that will fit on a 6 mm motor mount shaft on IRIS+.

  * Use the 6 mm propeller adapter rings with your 10&#215;4.7&#8243; SlowFly propeller. Both for APC and HQProp this will be the largest ring in the set of 4 rings that comes with your propeller.
  * Mount the propeller on the motor. The propellers marked with &#8220;R&#8221; will go on the silver motor mount. These propellers will spin clockwise. The propellers without the &#8220;R&#8221; mark will go on the black motor mounts and will spin counter-clockwise. Press the propeller all the way down on the motor mount.
  * Place the <a href="http://amzn.to/2eFdyOc" target="_blank">DJI Phantom Prop Aluminum Alloy Replacement Nuts</a> on the motor mounts. The silver nut will go on the black motor mount and the black nut will go on the silver motor mount.
  * Carefully tighten the nuts on the motor mounts, first with your fingers, then with the wrench that came with the nuts for the nuts as well as the wrench that came with your IRIS+ for the motor mount.

The final assembly of the 10&#215;4.7&#8243; propellers on IRIS+ can be seen in Figure 3 and Figure 4.

<div id="attachment_227" style="width: 178px" class="wp-caption aligncenter">
  <a href="https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/clockwise/"><img class="wp-image-227 size-medium" src="/content/uploads/2014/10/clockwise.jpg?w=168" alt="Figure 5: IRIS+ with 10x4.7&quot; propellers (clockwise version)" width="168" height="300" srcset="/content/uploads/2014/10/clockwise.jpg 1836w, /content/uploads/2014/10/clockwise-168x300.jpg 168w, /content/uploads/2014/10/clockwise-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

  <p class="wp-caption-text">
    Figure 5: IRIS+ with 10&#215;4.7&#8243; propellers (clockwise version)
  </p>
</div>

<div id="attachment_228" style="width: 178px" class="wp-caption aligncenter">
  <a href="https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/counter-clockwise/"><img class="wp-image-228 size-medium" src="/content/uploads/2014/10/counter-clockwise.jpg?w=168" alt="Figure 6: IRIS+ with 10x4.7&quot; propellers (counter-clockwise version)" width="168" height="300" srcset="/content/uploads/2014/10/counter-clockwise.jpg 1836w, /content/uploads/2014/10/counter-clockwise-168x300.jpg 168w, /content/uploads/2014/10/counter-clockwise-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

  <p class="wp-caption-text">
    Figure 6: IRIS+ with 10&#215;4.7&#8243; propellers (counter-clockwise version)
  </p>
</div>

We are now ready to test our new propellers with either a Loiter test or a real mission. Figure 5 shows a Loiter test: Hover throttle is between 55% and 65% and flight time is also around 15 minutes.

<div id="attachment_236" style="width: 615px" class="wp-caption aligncenter">
  <a href="https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/iris_5100mah_loiter_newprops/"><img class="wp-image-236 size-large" src="/content/uploads/2014/10/iris_5100mah_loiter_newprops.png?w=605" alt="Figure 7: Loiter test with IRIS+ on 5100 mAh battery with 10x4.7&quot; SlowFlyer propeller" width="605" height="140" srcset="/content/uploads/2014/10/iris_5100mah_loiter_newprops.png 1366w, /content/uploads/2014/10/iris_5100mah_loiter_newprops-300x69.png 300w, /content/uploads/2014/10/iris_5100mah_loiter_newprops-1024x238.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 7: Loiter test with IRIS+ on 5100 mAh battery with 10&#215;4.7&#8243; SlowFlyer propeller
  </p>
</div>

Note that you cannot compare the flight time in Figure 5 with the one in Figure 2 as I did not initiate the landing based on the same condition (voltage or mAh drawn).

Figure 6 shows an auto mission flown with IRIS+ and a full FPV kit (All up weight 1665g) on HQProp 10&#215;4.7 Slow Flyer propellers. The mission continues beyond the 11 minute mark shown in the graph.

<div id="attachment_229" style="width: 615px" class="wp-caption aligncenter">
  <a href="https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/iris_5100mah_newprops/"><img class="wp-image-229 size-large" src="/content/uploads/2014/10/iris_5100mah_newprops.png?w=605" alt="Figure 8: IRIS+ with 10x4.7&quot; SlowFly propellers" width="605" height="140" srcset="/content/uploads/2014/10/iris_5100mah_newprops.png 1366w, /content/uploads/2014/10/iris_5100mah_newprops-300x69.png 300w, /content/uploads/2014/10/iris_5100mah_newprops-1024x238.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 8: IRIS+ with 10&#215;4.7&#8243; SlowFly propellers
  </p>
</div>

Looking at the current drawn with the 10&#215;4.7&#8243; propellers, we can see that it is at around the same level as with the 9.5&#215;4.5&#8243; propellers (See Figure 9). The more &#8220;spiky&#8221; Amps curve is caused by slightly higher wind during this test than with the original props.

<div id="attachment_292" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps.png"><img class="wp-image-292 size-large" src="/content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-1024x238.png" alt="Figure 9: Current drawn during flight with IRIS on 5100 mAh battery with 10x4.7&quot; propellers" width="605" height="140" srcset="/content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-1024x238.png 1024w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-300x69.png 300w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-100x23.png 100w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-150x34.png 150w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-200x46.png 200w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-450x104.png 450w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-600x139.png 600w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps-900x209.png 900w, /content/uploads/2014/10/IRIS-_5100mAh_Loiter_NewProps_Amps.png 1366w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 9: Current drawn during flight with IRIS on 5100 mAh battery with 10&#215;4.7&#8243; propellers
  </p>
</div>

The only drawback of using these 10&#215;4.7&#8243; propellers vs. the stock IRIS+ 9.5&#215;4.5&#8243; propellers is that they are not spin on/off propellers. It therefore takes a bit longer and requires tools to mount or un-mount the propellers.

But in return they provide you great lift capacity for the rather heavy IRIS+. Therefore after a few dozen test flights with 10&#215;4.7&#8243; propellers, I&#8217;m certainly not thinking about mounting the 9.5&#215;4.5&#8243; propellers ever again. I&#8217;ve flown the quad at  40 kmh / 25 mph in high wind and gusts at even 100 m / 300 ft altitude, without noticing any bad behavior.
