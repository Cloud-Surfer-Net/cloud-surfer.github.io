---
id: 77
title: 3DR IRIS with 4S batteries
date: 2014-07-14T12:20:25+00:00
author: Christian Elsen
layout: post
permalink: /2014/07/14/3dr-iris-with-4s-batteries/
redirect_from: 
  - /2014/07/14/3dr-iris-with-4s-batteries/amp/
image: /content/uploads/2014/07/4s_props1.png
thumbnail: /content/uploads/2014/07/4s_props1-150x150.png
categories:
  - 3DR IRIS
  - Power and Motors
tags:
  - work-in-progress
---
Due to the rather [poor flight performance](https://www.cloud-surfer.net/2014/07/10/3dr-iris-with-gimbal-and-tall-legs-is-too-heavy-to-fly-safely/ "3DR IRIS with Gimbal and tall legs is too heavy to fly safely?") of the 3DR IRIS with Gimbal and long legs on 3S batteries, I was looking into flying with 4S batteries, along with reducing the weight of the quad. In this post I want to share my interim results.

**Note: These are interim results as I&#8217;m still working out some quirks. Also 3DR has not officially approved this flight configuration. Try it at your own risk!**

**Note: Do not use 4S batteries with the new IRIS+. On the IRIS+ 3DR has replaced the previous 850kV motors with 920kV motors. These motors are unsuited for usage with 4S batteries. The propellers would spin faster than their specified maximum.**

**Reducing weight**

The only approach I&#8217;ve taken so far to reduce the weight of IRIS is by using 3D printed tall legs from <a href="http://www.dingprint.de/" target="_blank">dingprint.de</a>. They are lightweight, yet robust enough. A set of 4 legs weights 38g and therefore as much as a single leg of the stock 3DR legs. See more about these legs <a href="https://www.rcgroups.com/forums/showthread.php?t=2046042" target="_blank">here</a> under _Update 9_.

While these legs are produced and shipped from Germany, you can purchase similar legs in the US. Contact <promo@impconcepts.com> and ask about the 6&#8243;- Custom Blue 3D Printed 3DR IRIS legs.

The all up weight (AUW) of IRIS with these legs as well as the 4S battery (more on this later) is now 1659g.

**Going from 3S to 4S lipos**

4S lipos use 4 cells in serial and therefore reach a nominal voltage of 14.8V. If you increase the battery voltage by 33% (3S to 4S) then you are effectively increasing the motor speed by 33%. To keep all things equal you need to decrease the prop size to match this increased motor speed and prevent the motors from heating up. Once at the same wattage (roughly the same speed and thrust in flight) you would draw 33% less current, and therefore  get about 33% longer flying time. The reasoning behind that is: Watts = Volts x Amps. Thus increase volts by 33%, then drop amps x 33% for same watts.

If you don&#8217;t decrease the prop size, the faster spinning prop will generate a lot more speed and a lot more current, increasing the watts very significantly. The resulting effect will be a higher powered (lower hover throttle) quad, with a higher current draw (resulting in shorter flight times). You may also run the risk of overheating your motors or drawing more current than the ESC can handle. This is obviously not desired. Although we do want to increase the power slightly vs. the 3S config.

Also keep in mind that not all equipment can handle the higher voltage of 4S batteries. The Tarot Gimbal cannot handle this voltage and therefore needs a voltage regulator. If you are using additional FPV equipment, you also need to check if they can handle the maximum 16.8V that 4S brings.

**Material for testing**

For testing IRIS with 4S batteries, we need a 4S Lipo, but also smaller propellers. Here is what I&#8217;m using for the tests:

  * <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=18637&aff=1269428" target="_blank">ZIPPY Flightmax 3000mAh 4S1P 20C</a> from HobbyKing. This battery is very cheap and delivers roughly as much wattage as a 3S-4000mAh battery. It fits the IRIS battery bay perfectly and already comes with an XT-60 plug. I already own a <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=30917&aff=1269428" target="_blank">IMAX B6-AC Charger/Discharger</a>, which is capable of charging these batteries without any issues.
  * APC SlowFly 9&#215;4.7 <a href="http://www.getfpv.com/propellers/apc-9x4-7-sfp.html" target="_blank">Pusher</a> and <a href="http://www.getfpv.com/propellers/apc-9x4-7-sf.html" target="_blank">Puller</a> propellers. They are basically the same propeller as the stock propellers that come with IRIS, except that they are 9&#8243; in outer diameter instead of 10&#8243;. As they use the same spacer rings for the propeller shaft, you can even leave your current ones on IRIS.
  * <a href="http://www.multiwiicopter.com/products/fpv-voltage-bec-regulator-12v-4s" target="_blank">Voltage regulator from 4S (16.8V) to 12V</a>. The Tarot Brushless Gimbal is recommended to be operated with 12V and cannot handle voltages higher than 14.8V. We therefore need to place a voltage regular between the 4S battery and the Gimbal. This will reduce the voltage from up to 16.8V on the lipo side to 12V for the Gimbal. As the Gimbal only draws a maximum of 500 mA, the linked voltage regular is a perfect choice. Also the regulator already comes with the right plugs, is very small and lightweight.

**Crunching the numbers**

Before heading out to the flying field with the IRIS, 4S batteries and 9&#215;4.7 propellers, lets crunch the numbers in <a href="http://www.ecalc.ch/xcoptercalc.php" target="_blank">eCalc xcopterCalc</a> and see what to expect. With xcopterCalc I will also include an APC Slowfly 10&#215;3.8 propeller. This propeller has the same length as the stock IRIS propellers, but a different pitch.

While I have already shown all values that I use for eCalc xcopterCalc in a [previous post](https://www.cloud-surfer.net/2014/07/10/3dr-iris-with-gimbal-and-tall-legs-is-too-heavy-to-fly-safely/ "3DR IRIS with Gimbal and tall legs is too heavy to fly safely?"), this time I also want to include expected motor temperatures. Here you can chose between &#8220;Excellent&#8221;, &#8220;Good&#8221;, &#8220;Medium&#8221;, &#8220;Poor&#8221;, and &#8220;Very Poor&#8221; with &#8220;Medium&#8221; being the default in eCalc. It is hard to determine the correct setting here. the best approach is to measure the real motor temperature during test flight and re-verse calculating it. For now I&#8217;ll stick to the setting &#8220;Poor&#8221; due to the motor pockets of the IRIS arms.

While I managed to reduce the weight as written before, I&#8217;ll still crunch the numbers with the stock weight of IRIS with 1692g, just to have some safety buffer &#8211; e.g. for installing FPV gear.

With that here are the results:

<div id="attachment_88" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/07/4s_props.png"><img class="wp-image-88 size-large" src="/content/uploads/2014/07/4s_props.png?w=605" alt="Figure 1: eCalc simulation of 3DR IRIS with 4S battery" width="605" height="348" srcset="/content/uploads/2014/07/4s_props.png 1020w, /content/uploads/2014/07/4s_props-300x172.png 300w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 1: eCalc simulation of 3DR IRIS with 4S battery
  </p>
</div>

We can see that the stock 10&#215;4.7 propeller is not a good choice. At low outside temperatures we run the risk of drawing more ampere during full throttle than the ESC can handle. Also the expected motor temperatures become higher quite quickly.

Both the 10&#215;3.8 as well as the 9&#215;4.7 propeller will provide decent hover throttle values at Normal and Low battery. The 9&#215;4.7 propeller provides slightly more promising motor temperatures at max throttle. These temperatures are expecte to be only slightly higher than with the stock 3S-3500mAh configuration.

**Bench testing**

Next comes the &#8220;bench testing&#8221;, flying IRIS with 4S-3000mAh batteries and 9&#215;4.7 propellers. For this I attached the IRIS &#8211; via chopsticks &#8211; to a laundry drying rack on the floor. That way I can simulate a &#8220;flight&#8221; indoors without IRIS actually taking off (See Figure 2).

<div id="attachment_89" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/07/2014-07-11-21-17-48.jpg"><img class="size-medium wp-image-89" src="/content/uploads/2014/07/2014-07-11-21-17-48.jpg?w=300" alt="Figure 2: Bench-testing IRIS with 4S batteries" width="300" height="168" srcset="/content/uploads/2014/07/2014-07-11-21-17-48.jpg 3264w, /content/uploads/2014/07/2014-07-11-21-17-48-300x168.jpg 300w, /content/uploads/2014/07/2014-07-11-21-17-48-1024x576.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 2: Bench-testing IRIS with 4S batteries
  </p>
</div>

With this test-setup I hooked up IRIS to Mission Planner in order to monitor voltage, ampere, and hover throttle. Next I armed IRIS and gave enough throttle to have lift up and be held back by the chopsticks. This could be considered hover throttle. See Figure 3 for the throttle curve for one sample flight.

<div id="attachment_91" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/07/benchtest1.png"><img class="wp-image-91 size-large" src="/content/uploads/2014/07/benchtest1.png?w=605" alt="Figure 3: Hover-Throttle during bench test" width="605" height="160" srcset="/content/uploads/2014/07/benchtest1.png 1920w, /content/uploads/2014/07/benchtest1-300x79.png 300w, /content/uploads/2014/07/benchtest1-1024x272.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 3: Hover-Throttle during bench test
  </p>
</div>

During these test flights the motor did not get noticeable warm and only reached a temperature of about 30C, which matches roughly the expected result. I measured the temperature with a <a href="https://www.amazon.com/gp/product/B00GM7KAR8/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B00GM7KAR8&linkCode=as2&tag=cloudsurfer-20&linkId=H73ANZMZNOQRLSJX" target="_blank">contactless IR thermometer</a>.

**Outdoor flight test**

Next on the agenda were outdoor flight tests with the 4S-3000 mAh and 9&#215;4.7 propellers. For this I loaded the <a href="https://github.com/ArduPilot/ardupilot/blob/master/Tools/Frame_params/Iris%20with%20Tarot%20Gimbal.param" target="_blank" rel="nofollow">Iris with Tarot Gimbal</a> parameter file and performed an <a href="http://ardupilot.org/copter/docs/autotune.html" target="_blank">Auto Tune</a> once airborne. Also I configure the <a href="http://ardupilot.org/copter/docs/parameters.html#Throttle-Mid-Position-(ArduCopter-THR_MID)" target="_blank">THR_MID parameter</a> to be 570, in order to better match the expected hover throttle.

Be aware that with the 4S battery IRIS behaves much more sensitive on the throttle stick. You can feel the &#8220;power&#8221; that IRIS has now &#8211; despite the weight of the Tarot Gimbal and tall legs.

My full parameter file for IRIS with Gimbal and 4S-3000mAh batteries can be found here.

Outdoor flight tests were very successful. I was able to use multiple 4S-3000mAh lipo to repeatedly fly an Auto mission for about 8-9 minutes per battery. Afterwards remaining Lipo capacity was at about 30%, which provides a very conservative buffer. Reducing this buffer to about 20% would probably add another 1 minute of flight time. During the entire flight the throttle remained around 58% &#8211; 60% for flying &#8211; not hovering (Figure 4).

<div id="attachment_92" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/07/outdoor_flight_test01.png"><img class="wp-image-92 size-large" src="/content/uploads/2014/07/outdoor_flight_test01.png?w=605" alt="Figure 4: Outdoor flight test" width="605" height="160" srcset="/content/uploads/2014/07/outdoor_flight_test01.png 1920w, /content/uploads/2014/07/outdoor_flight_test01-300x79.png 300w, /content/uploads/2014/07/outdoor_flight_test01-1024x272.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 4: Outdoor flight test
  </p>
</div>

The entire log for this flight can be found here. After each flight the motor temperature was around 32-34C, while the outside temperature was around 20C. This again roughly confirmed the eCalc xcopterCalc numbers.

With the 4S battery IRIS with long legs and Gimbal flies similar to IRIS with short legs and 3S batteries. While it&#8217;s still far from an Acro-Quad, you at least can&#8217;t feel the weight dragging IRIS down anymore.

**10&#215;3.8 Propellers**

I also tested flying IRIS with APC SlowFly 10&#215;3.8 propellers. These propellers have an outer diameter of 10&#8243; &#8211; just like the stock propellers that come with IRIS. But the pitch is less with 3.8&#8243; per full rotation vs. 4.7&#8243; per full rotation with the stock propellers.

Comparing the flight behavior of IRIS between the 9&#215;4.7 configuration and the 10&#215;3.8 behavior, here are the main differences and benefits of each configuration.

With 9&#215;4.7 propellers

  * Flight time 9-10 minutes up until 20% battery remaining
  * Motors get moderately hot with about 35C at 20C outside temperature
  * The quad performs very well in windy/gusty conditions and drifts off less from desired path/location

With 10&#215;3.8 propellers

  * Flight time 10-10 1/2 minutes up until 20% battery remaining
  * Motors get hot with about 45 &#8211; 50C at 20C outside temperature
  * The quad is susceptible to windy/gusty conditions and drifts off from desired path/location due to the larger propellers acting like a sail.

With this I personally prefer to fly the configuration with a 9&#215;4.7 propeller, due to the superior performance in windy conditions.

**Summary**

IRIS with Gimbal and tall legs behaves quite well flying on a 4S-3000mAh battery and 9&#215;4.7 propellers. Hover throttle is within a reasonable range and IRIS has enough &#8220;power&#8221; to fly around without any issues, even towards the end (30% remaining energy) of a Lipo. Fligh time is decent while not great with 8-9 minutes. You can further increase flight time by about 1 minute by reducing the Lipo safety buffer to 20% remaining energy at landing, giving you a total flight time of 9 &#8211; 10 minutes.

While there are other ways to improve the flight performance of IRIS, the benefits of the approach shown here should be clear: It requires very few investments into a new 4S-3000mAh lipo and 9&#215;4.7 propellers. It also requires a minimal work to be performed with swapping only the propellers and battery. No soldering is required as it would be with e.g. changing the motors.

**What&#8217;s next?**

With the 4S battery IRIS behave very sensitive on the throttle stick. You can feel this while flying in Stabilize mode. I have attempted to compensate for this by reducing the Throttle acceleration controller <a href="http://ardupilot.org/copter/docs/parameters.html#Throttle_acceleration_controller_P_gain_ArduCopterTHR_ACCEL_P" target="_blank">P</a> and <a href="http://ardupilot.org/copter/docs/parameters.html#Throttle_acceleration_controller_I_gain_ArduCopterTHR_ACCEL_I" target="_blank">I</a> gain. Unfortunately I have found contradicting reports whether the Throttle acceleration controller <a href="http://ardupilot.org/copter/docs/parameters.html#Throttle_acceleration_controller_P_gain_ArduCopterTHR_ACCEL_P" target="_blank">P</a> and <a href="http://ardupilot.org/copter/docs/parameters.html#Throttle_acceleration_controller_I_gain_ArduCopterTHR_ACCEL_I" target="_blank">I</a> gains actually affect Stabilize mode or not. If they don&#8217;t, I will need to look into R/C transmitter curves.

The flight time of IRIS would improve if weight could be reduced even further. This is an area were I would love to hear ideas on how to do this on IRIS without having to rebuild the quad into a new machine.

Also a larger 4S battery could increase flight time. With a 4S-4500mAh battery one would be able to reach flight times of approximately 12 minutes. Unfortunately 4S batteries at this capacity that have the right size to fit IRIS are either <a href="http://mikrokopter.altigator.com/4500mah-4s-lipo-35c-p-41537.html" target="_blank">out of stock</a> or <a href="https://www.electricwingman.com/desire-power-35c-3300mah-4s-lipo-battery.aspx" target="_blank" rel="nofollow">not available in the US</a>. Other batteries that <a href="http://www.getfpv.com/lumenier-4200mah-4s-35c-lipo-battery.html" target="_blank">are readily available in the US</a> don&#8217;t fit the size of the IRIS battery bay. Here it would also be great if someone had an idea how to easily solve this.

&nbsp;
