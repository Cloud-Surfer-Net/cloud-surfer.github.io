---
id: 136
title: High HDOP values when flying IRIS
date: 2014-09-12T12:21:40+00:00
author: Christian Elsen
layout: post
permalink: /2014/09/12/high-hdop-values-when-flying-iris/
redirect_from: 
  - /2014/09/12/high-hdop-values-when-flying-iris/amp/
image: /content/uploads/2014/09/xdop_berkeley-672x372.png
thumbnail: /content/uploads/2014/09/xdop_berkeley-150x150.png
categories:
  - 3DR IRIS
  - Sensors
tags:
  - gps
  - ublox
---
In the IRIS forums at <a href="http://diydrones.com/group/iris" target="_blank">DIYDronres</a>, <a href="http://ardupilot.org/?f=48" target="_blank">Ardupilot</a>, and the <a href="https://www.facebook.com/groups/635611993176188/" target="_blank">IRIS Facebook group</a> I have seen reports from various users who have complained about low <a href="https://en.wikipedia.org/wiki/Dilution_of_precision_(GPS)" target="_blank">HDOP (Horizontal Dilution of precision)</a> reported by their IRIS when trying to arm in Loiter or Auto mode (Both are GPS assisted modes). In these cases the HDOP value determined and reported by Arducopter is higher than 2.0 after powering up IRIS. This value is higher than the default value of 2.0 for the <a href="http://ardupilot.org/copter/docs/parameters.html#GPS-Hdop-Good-(ArduCopter-GPS_HDOP_GOOD)%20" target="_blank">GPS_HDOP_GOOD paramter</a> value. As a result the pre-arm checks fail and IRIS is not able to arm in a GPS-assisted flight mode.

I&#8217;m facing this situation in probably 8-9 out of 10 flights. Yet, when arming IRIS and taking off manually in Stabilize mode I&#8217;m able to switch into Loiter mode right after takeoff. While the HDOP value reported by IRIS via DroidPlanner2 would still be above 2.0, the vehicle does not show any negative performance with regards to GPS. In fact IRIS would remain in position quite well within a 1m x 1m x 1m or even smaller &#8220;box&#8221; in the sky. There is no twitching or leaving this very precise location.

So what could be the reason between the GPS module on IRIS actually working pretty well and the reported &#8220;quality&#8221; number being so low?

**Finding the underlying bug**

I did a lot of digging – and I mean a lot of digging – and even thought about replacing my 3DR GPS module that only supports GPS with a <a href="http://www.virtualrobotix.it/index.php/it-IT/shop-virtualrobotix?error=404" target="_blank">module</a> that also supports GLONASS, BeiDou and Galileo. The added number of satellites &#8211; especially from GLONASS &#8211; should result in lower HDOP values.

And then I stumbled over the <a href="https://github.com/ArduPilot/ardupilot/pull/644" target="_blank">Ardupilot bug #644</a>. It states that the value reported back from the GPS module for HDOP isn’t actually HDOP but PDOP (Position (3D) Dilution of precision). So what? Isn’t that close enough. Turns out, it’s not!

**How does HDOP and PDOP differ?**

Let’s use the tool http://satpredictor.navcomtech.com/ and determine the expected xDOP values for the location of the 3DR Berkeley office based on a 10 degree elevation mask. This means that satellites below a 10 degree angle are not visible due to trees, building or mountains (See Figure 1). It is the default value for the above tool and a reasonable assumption.

<div id="attachment_137" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/elevation_mask.png"><img class="size-medium wp-image-137" src="/content/uploads/2014/09/elevation_mask.png?w=300" alt="Figure 1: The concept of an elevation mask" width="300" height="239" srcset="/content/uploads/2014/09/elevation_mask.png 458w, /content/uploads/2014/09/elevation_mask-300x239.png 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 1: The concept of an elevation mask
  </p>
</div>

Let&#8217;s have a look and the predicted xDOP values for the above location on Friday, September 12th 2014 (See Figure 2). Any other date or location will yield similar results.

<div id="attachment_138" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/xdop_berkeley.png"><img class="size-medium wp-image-138" src="/content/uploads/2014/09/xdop_berkeley.png?w=300" alt="Figure 2: xDOP values in Berkeley, CA" width="300" height="167" srcset="/content/uploads/2014/09/xdop_berkeley.png 1906w, /content/uploads/2014/09/xdop_berkeley-300x167.png 300w, /content/uploads/2014/09/xdop_berkeley-1024x570.png 1024w, /content/uploads/2014/09/xdop_berkeley-672x372.png 672w, /content/uploads/2014/09/xdop_berkeley-1038x576.png 1038w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 2: xDOP values in Berkeley, CA
  </p>
</div>

We can see a very interesting result:

You can see the values for HDOP &#8211; shown in grey at the bottom. That’s the values that our autopilot in IRIS believes it is receiving from the GPS module and what is being displayed in Droidplanner2 or Mission Planner.  Notice that I highlighted the 2.0 xDOP line in red, which corresponds to the cut-off value based on which IRIS makes the decision to arm or not. Thus we can see that HDOP for this location and date is always below 2.0. That&#8217;s great! With that we should be able to always arm IRIS in Loiter or Auto at that location and on that day.

But you can also see the PDOP &#8211; shown in green. That’s what the autopilot of IRIS is really receiving  from the GPS module, instead of HDOP. Notice that quite frequently this PDOP value is higher than 2.0, often much higher. During these periods &#8211; when the PDOP is higher than 2.0 &#8211; IRIS will not arm, even though the corresponding HDOP would be low enough. These are the moments when I&#8217;m attempting my 8-9 out of the 10 flights that I mentioned before.

**How to fix this?**

Ideally the above mentioned <a href="https://github.com/ArduPilot/ardupilot/pull/644" target="_blank">Ardupilot bug #644</a> should be fixed as soon as possible. That way the Autopilot of IRIS would actually make decisions on the correct value. Also we would see the correct HDOP value in DroidPlanner2 or Mission Planner.

In the meantime, I’ll increase the parameter value of GPS\_HDOP\_GOOD to 2.5 or 3.0. Looking at above graph, a PDOP of 3.0 would correspond to a HDOP of 2.0 for that location and time. From what I can tell, increasing this value should not have a negative effect, but rather allow me to arm IRIS in Loiter or AUto mode much more frequently.

Other that that I would also like to see a module from 3DR that supports GPS, GLONASS, BeiDou and Galileo. If Virtual Robotix in Italy can <a href="http://www.virtualrobotix.it/index.php/it-IT/shop-virtualrobotix?error=404" target="_blank">offer one</a>, 3DR should be able to offer a plug&play replacement of their current module.
