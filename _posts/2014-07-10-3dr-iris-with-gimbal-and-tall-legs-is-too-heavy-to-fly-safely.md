---
id: 23
title: 3DR IRIS with Gimbal and tall legs is too heavy to fly safely?
date: 2014-07-10T14:32:17+00:00
author: Christian Elsen
layout: post
permalink: /2014/07/10/3dr-iris-with-gimbal-and-tall-legs-is-too-heavy-to-fly-safely/
image: /content/uploads/2014/07/iris_side_with_gimbal-600x372.jpg
thumbnail: /content/uploads/2014/07/iris_side_with_gimbal-150x150.jpg
categories:
  - 3DR IRIS
tags:
  - power
  - safety
---
In the IRIS forums at <a href="http://diydrones.com/group/iris" target="_blank">DIYDronres</a>, <a href="http://ardupilot.org/?f=48" target="_blank">Ardupilot</a>, and the <a href="https://www.facebook.com/groups/635611993176188/" target="_blank">IRIS Facebook group</a> I have seen reports from various users who have either complained about poor flight performance of their IRIS, or had crashes due to performance loss towards the end of a flight. All these issues happened while flying IRIS with tall legs and gimbal. As I just wanted to start flying with this combination, I wanted to find out what could be the reason for these issues and crashes. In the end I don&#8217;t want my IRIS to crash.

I therefore decided to take IRIS&#8217; stock configuration data and use <a href="http://www.ecalc.ch/xcoptercalc.php" target="_blank">xcopterCalc</a> to determine the performance characteristics.

**Note:** With the updated IRIS+ the weight has been decreased and the performance of the used motors has improved. Therefore some of the issues described here have improved or can be [improved by the pilot](https://www.cloud-surfer.net/2014/10/10/improving-lift-on-iris-with-other-propellers/ "Improving lift on IRIS+ with other propellers").

**Weight of a stock IRIS**

The weight of a stock IRIS with tall legs and gimbal is as follows according to the specification of 3DR as well as GoPro.

  * IRIS with battery: 1282 g
  * Tall Legs: 4x 34 g = 136 g
  * Tarot T-2D: 200 g
  * GoPro Hero3: 74 g
  * **Total: 1692 g**

The total weight of IRIS (All Up Weight; AUW) is therefore 1692 g or 59.7 oz.

**xcopterCalc test scenarios**

With the above weight I went through a series of test scenarios at different flying field altitudes and air temperatures. Both altitude and air temperature influences the flying performance with regards to required throttle to keep the quadcopter in the air, but also flight time.

The values used for <a href="http://www.ecalc.ch/xcoptercalc.php" target="_blank">xcopterCalc</a> were:

  * Number of Rotors: 4
  * Model Weight: 1692g (incl. Drive)
  * Elevation: see table below
  * Air Temperature: see table below
  * Battery Cell: Custom
  * Configuration: 3S1P
  * Cell Capacity: 3500 mAh
  * Resistance: 0.0052 Ohm
  * Voltage: 3.7V
  * C-Rate: 30C cont, 40C max
  * Controller: max 20A
  * Motor Manufacturer: RCTimer A2830-12 (850)
  * Propeller: APC SlowFly SF
  * Diameter: 10
  * Pitch: 4.7
  * Number of blades: 2

Note: You might have to <a href="http://www.ecalc.ch/calcmember/signup.htm" target="_blank" rel="nofollow">subscribe</a> to xcopterCalc in order to use all above settings.

For altitude above sea level (ASL), air temperature and <a href="http://www.engineeringtoolbox.com/air-altitude-pressure-d_462.html" target="_blank">resulting Air Pressure</a> I decided to use the following combinations:

  * ASL: 0 m, Air Temperature: 5 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 10 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 15 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 20 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 25 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 30 C, 1010 hPa
  * ASL: 0 m, Air Temperature: 35 C, 1010 hPa
  * ASL: 500 m, Air Temperature: 20 C, 995 hPa
  * ASL: 1000 m, Air Temperature: 20 C, 977 hPa
  * ASL: 1500 m, Air Temperature: 20 C, 960 hPa
  * ASL: 2000 m, Air Temperature: 20 C, 942 hPa

**xcopterCalc test results**

The result of the above xcopterCalc scenarios were quite surprising:

<div id="attachment_25" style="width: 615px" class="wp-caption alignnone">
  <a href="/content/uploads/2014/07/iris_gimbal_talllegs_flighttimes.png"><img class="wp-image-25 size-large" src="/content/uploads/2014/07/iris_gimbal_talllegs_flighttimes.png?w=605" alt="Figure 1: Hover Throttle and Flight times for 3DR IRIS with Gimbal and tall legs" width="605" height="186" srcset="/content/uploads/2014/07/iris_gimbal_talllegs_flighttimes.png 785w, /content/uploads/2014/07/iris_gimbal_talllegs_flighttimes-300x92.png 300w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 1: Hover Throttle and Flight times for 3DR IRIS with Gimbal and tall legs
  </p>
</div>

**Interpretation of results**

Looking at the table above, the &#8220;Hover Throttle (Normal)&#8221; is the amount of throttle (in percent of total possible throttle) required at the beginning of a flight with a fresh battery to keep IRIS hovering. The &#8220;Hover Throttle (Low)&#8221; is the amount of throttle required when the battery is down to 25% capacity. A battery capacity of 25% is about when you should land in order to give you enough buffer to not drain more than 80% of your battery capacity.

Unfortunately it becomes very clear: IRIS is not suitable to be flown with the above weight at any realistic air temperature or altitude: The required hover throttle is always higher than 70% (making it a &#8220;very underpowered copter&#8221; according to <a href="http://ardupilot.org/copter/docs/ac_throttlemid.html" target="_blank" rel="nofollow">http://copter.ardupilot.com/wiki/ac_throttlemid/</a>). But in all cases the required hover throttle goes even beyond 80% towards the end of the flight. It&#8217;s almost impossible to control a quadcopter at that required hover level.

Therefore my recommendation: Don&#8217;t fly your stock IRIS with Gimbal and long legs! It&#8217;s not safe and you run a very high risk of crashing it!

**Theory vs. Real Life

**

It is very easy to verify above theoretical results with real life flights as it is very easy to determine your required Hover Throttle from log files. Here is how to do this:

  * Fly IRIS in Stabilize, AltHold or Loiter in a stable hover for 30-60 seconds.
  * Download the logs from IRIS for that flight
  * Open the log file in Mission Planner via Terminal -> Log Browse.
  * In the right-hand tree open the &#8220;CTUN&#8221; subfolder. Click the tick box for &#8220;ThrOut&#8221;.
  * Find the stable hover period of your flight (white box in example below) and read the approx value of that period (white line in example below).

    You will see that in the example below it is about 84%.

<div id="attachment_27" style="width: 615px" class="wp-caption alignnone">
  <a href="/content/uploads/2014/07/determine_hover_throttle_overlay.png"><img class="wp-image-27 size-large" src="/content/uploads/2014/07/determine_hover_throttle_overlay.png?w=605" alt="Figure 2: Determine Hover Throttle via Arducopter logs" width="605" height="160" srcset="/content/uploads/2014/07/determine_hover_throttle_overlay.png 1920w, /content/uploads/2014/07/determine_hover_throttle_overlay-300x79.png 300w, /content/uploads/2014/07/determine_hover_throttle_overlay-1024x272.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 2: Determine Hover Throttle via Arducopter logs
  </p>
</div>

Furthermore in this example you can see that the pilot had to give 100% throttle a few times to keep the quad in the air. This is clearly not a safe way to fly.

**How to improve the flight performance and characteristic**

In order to improve the flight performance and characteristic of an underpowered quadcopter there are a few things that can be done:

  * Increasing the power of the motors and ESCs
  * Use a higher voltage battery (i.e. switch from a 3S to a 4S battery)
  * Reduce the weight of the quadcopter
  * Change the used propeller (Diameter and/or Pitch)

For this let&#8217;s have a quick look at the effect of weight on the flight time and required hover throttle. We will use the same test scenario above at 0 m ASL for the flying field altitude and air temperature of 20C. Next we will decrease the weight of IRIS in 50g / 1.76 oz  increments.

<div id="attachment_30" style="width: 615px" class="wp-caption alignnone">
  <a href="/content/uploads/2014/07/iris_weight_flighttimes.png"><img class="size-large wp-image-30" src="/content/uploads/2014/07/iris_weight_flighttimes.png?w=605" alt="Figure 3: IRIS fligh times and hover throttle based on weight" width="605" height="150" srcset="/content/uploads/2014/07/iris_weight_flighttimes.png 806w, /content/uploads/2014/07/iris_weight_flighttimes-300x74.png 300w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 3: IRIS fligh times and hover throttle based on weight
  </p>
</div>

We can see that we would have to reduce the weight to 1442g or below in order to ensure that the hover throttle stays below 70% even towards the end of the flight. Keep in mind that these values hold true for flying at sea level. If you want to fly at higher altitudes, e.g. In Denver, CO you will need to decrease weight even more.

This means that reducing weight is probably not enough. It is also questionable how to reduce weight to the required extend while still using a Gimbal.

**What to do next?**

As changing the motors and ESCs of IRIS not only requires procuring new equipment but also soldering these together, I consider that option out of scope. But all other options &#8211; especially a combination of them &#8211; are worth having another look. It is quite simple to swap a battery or the propellers.

Options for improving flight characteristics include:

  * Reducing the weight of IRIS by using different lighter legs
  * Using a 4S battery instead of a 3S battery.

    This requires changes to the used propeller in order to not overhead the motors. Possible options are 10&#215;3.8 or 9&#215;4.7 propeller instead of the stock 10&#215;4.7 propeller.

In the coming weeks I will run through various test scenarios with 4S batteries and different propellers and report back.
