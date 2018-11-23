---
id: 211
title: Battery Failsafe on IRIS+
date: 2014-10-06T17:56:26+00:00
author: Christian Elsen
layout: post
permalink: /2014/10/06/battery-failsafe-on-iris/
image: /content/uploads/2014/10/location-672x372.png
thumbnail: /content/uploads/2014/10/location-e1438904293921-150x132.png
categories:
  - 3DR IRIS
  - Power and Motors
tags:
  - battery
  - failsafe
  - fix
---
In the IRIS forums at <a href="http://diydrones.com/group/iris" target="_blank">DIYDronres</a>, <a href="http://ardupilot.org/?f=48" target="_blank">Ardupilot</a>, and the <a href="https://www.facebook.com/groups/635611993176188/" target="_blank">IRIS Facebook group</a> often the question comes up after the &#8220;best&#8221; or &#8220;right&#8221; battery failsafe setting for IRIS. After ruining one of my <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=56839&aff=1269428" target="_blank">Multistar 3S 5200mAh Lipo packs</a> over the weekend, I had a closer look at the various settings that influence what happens on a Battery Failsafe event. Therefore let&#8217;s have a look.

**What is a Failsafe for?**

First, let&#8217;s clarify what the purpose of a failsafe is. The idea here is to safely recover from a failure via smart software. In the case of the battery failsafe, the failure that we want to recover from is the battery running low on capacity. And the recovery is not having to use the battery any longer, which means being able to safely turn off the propulsion system, which is only possible after a successful landing. This doesn&#8217;t necessarily mean that the landing is at the same location that we took off from.

In other words: We want to bring IRIS to the ground safely before it runs out of energy and crashes. Such a crash could not only damage IRIS itself, but also other property or even harm people. It therefore has to be avoided.

Lipos loose voltage very abruptly once you reach a certain voltage (See Figure 2). You therefore want to stay away from this cliff-like voltage drop. Also in order to prolong the life of your Lipos you want to discharge only about 80% of the available capacity. In other words: For a 5100 mAh Lipo you only want to draw 4080 mAh.

The reason for such a failsafe is usually that we overestimated the available flight time, or that mechanism to display the current voltage / mAh have failed. This could e.g. be caused by DroidPlanner2 freezing or crashing on your tablet.

A failsafe event should not be part of your regular flying. In other words: Don&#8217;t fly every time until you hit the failsafe. Instead, treat it as an abnormal event.

**What happens by default for the Battery Failsafe?**

The default setting for triggering a battery failsafe in IRIS kicks in when the voltage of the battery is below 10.5V for at least 10 seconds continuously. Thus briefly reaching 10.4V and going back up to 10.5V won&#8217;t trigger a failsafe.

Also it is noteworthy to point out that the voltage triggering the failsafe can be changed via the <a href="http://ardupilot.org/copter/docs/parameters.html#Failsafe_battery_voltage_ArduCopterFS_BATT_VOLTAGE" target="_blank">FS_BATT_VOLTAGE parameter</a>.

But first, let&#8217;s have a look at what happens when the failsafe is actually triggered. For this let&#8217;s assume that IRIS is 300 m / 984 ft away from the launch point at an altitude of 100 m / 328 ft (See Figure 1). We will further assume that the failsafe action of RTL (Return to launch) is configured. The distance of 300 m / 984 ft from the launch point is chosen as this corresponds to the distance of the default geofence distance for IRIS.

<div id="attachment_212" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/location.png"><img class="wp-image-212 size-large" src="/content/uploads/2014/10/location.png?w=605" alt="Figure 1: IRIS on execution of Battery Failsafe" width="605" height="483" srcset="/content/uploads/2014/10/location.png 826w, /content/uploads/2014/10/location-300x239.png 300w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 1: IRIS on execution of Battery Failsafe
  </p>
</div>

In this case the current altitude of 100m / 328 ft is higher than the default <a href="http://ardupilot.org/copter/docs/parameters.html#RTL_Altitude_ArduCopterRTL_ALT" target="_blank">RTL_ALT</a> and therefore IRIS will not climb to this altitude. Instead IRIS will fly at the current altitude to the launch point. It will do so with the Loiter Horizontal Maximum Speed (<a href="http://ardupilot.org/copter/docs/parameters.html#Loiter_Horizontal_Maximum_Speed_WPNAV_LOIT_SPEED" target="_blank">WPNAV_LOIT_SPEED</a>) after using Waypoint Acceleration (<a href="http://ardupilot.org/copter/docs/parameters.html#Waypoint_Acceleration_WPNAV_ACCEL" target="_blank">WPNAV_ACCEL</a>). The default value for WPNAV\_LOIT\_SPEED is 600 cm/s, while the default value for WPNAV_ACCEL is 100 cm/s/s. Keep in mind that 600 cm is equal to 6 m.

In order to keep math simple we will leave aside acceleration. With this it will take IRIS approximately 300 m / 6 m/s = **50 s** to reach the launch point. (With acceleration in the picture IRIS would accelerate during the first 6 s from 0 m/s to 6 m/s. During that time IRIS would travel 16 m. Thus the exact time for IRIS to fly the 300 m / 328 ft would be 53.3 seconds).

Next IRIS will descent from the current altitude at 100 m / 328 ft to 10 m / 33 ft. It will do so with the Waypoint Descent Speed Target (<a href="http://ardupilot.org/copter/docs/parameters.html#Waypoint_Acceleration_WPNAV_ACCEL" target="_blank">WPNAV_SPEED_DN</a>). In this case the default value of 150 cm /s translates to 1.5 m / s. Therefore it will take IRIS ( 100 m &#8211; 10 m ) / 1.5 m/s = **60 s** to descent to 10m.

At this point IRIS will wait for RTL loiter time (<a href="http://ardupilot.org/copter/docs/parameters.html#RTL_loiter_time_ArduCopterRTL_LOIT_TIME" target="_blank">RTL_LOIT_TIME</a>) in order for the altitude measured by the barometer to stabilize. Here the default value is 5000 ms or **5s**.

After this IRIS will finally land with the Land speed (<a href="http://ardupilot.org/copter/docs/parameters.html#Land_speed_ArduCopterLAND_SPEED" target="_blank">LAND_SPEED</a>). In this case the default value is 50 cm/s or 0.5 m/s. Therefore it will take IRIS another 10 m / 0.5 m/s = **20s** to finally touch down.

If we add up all these times, we get 50s + 60s + 5s + 20s = **135 seconds**. In other words, it will take IRIS more than 2 minutes to get to the ground once the failsafe is triggered at this far location. Even if we change the failsafe action from RTL to LAND, it will still take 60s + 5s + 20s = **85 seconds**, that&#8217;s close to 1  1/2 minutes to get to the ground.

**How much energy is needed?**

At this point one should ask the question: Do I have enough energy for 135 seconds or 85 seconds of flight at 10.5V? Let&#8217;s have a look! The only benefit of ruining a Lipo in a failsafe event is having discharge data available beyond 10.5V and even beyond 9V. So let&#8217;s have a look.

<div id="attachment_213" style="width: 615px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/10/timing.png"><img class="wp-image-213 size-large" src="/content/uploads/2014/10/timing.png?w=605" alt="Figure 2: Discharge of Lipo beyond failsafe" width="605" height="209" srcset="/content/uploads/2014/10/timing.png 2558w, /content/uploads/2014/10/timing-300x103.png 300w, /content/uploads/2014/10/timing-1024x354.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

  <p class="wp-caption-text">
    Figure 2: Discharge of Lipo beyond failsafe
  </p>
</div>

At approximately 11 minutes 25 seconds into the flight the voltage has last reached the value of 10.5V. Therefore 10 seconds later, at 11:35 the battery failsafe will kick in. But even with the falsafe action set to LAND instead of RTL, it will still take us 85 seconds to get to the ground. That would bring us to 12:50. But at this point the voltage of the Lipo is already below 9V at 8.5V. This means that the Lipo has not only been damaged beyond repair, but we are lucky if IRIS doesn&#8217;t just drop out of the sky before that. Adding the 50 second flight time for bringing IRIS back to the launch point would definitely result in a crash due to loosing the propulsion system.

Above results are for my particular setup, but will most likely be very similar to yours.

What can we do? Just increase the failsafe voltage? Let&#8217;s see!

**Tuning the failsafe parameters**

Before we blindly increase the failsafe voltage, let&#8217;s see if we can&#8217;t tune the above parameters involved in the failsafe.

But before we do so, we take the decision not to use RTL as the failsafe action, but LAND. The reason is that first flying to the launch point would double or even more than double the time necessary to get IRIS safely on the ground. As outlined earlier: A failsafe event is an emergency event and we need to live with the fact that we now have to hike a few meters to pick up our hopefully non-damaged IRIS. Also keep in mind that you can still adjust the location while IRIS is performing a LAND action. You can therefore steer clear of minor objects while landing.

If you are flying over water, you&#8217;ll need to adapt this strategy obviously. But in the end handling the failsafe will always be about choosing the lesser evil.

First let&#8217;s increase the speed at which IRIS descends via the Waypoint Descent Speed Target (<a href="http://ardupilot.org/copter/docs/parameters.html#Waypoint_Acceleration_WPNAV_ACCEL" target="_blank">WPNAV_SPEED_DN</a>) value from 1.5 m / s to 2.5 m / s (or 250 cm /s). Although IRIS will not look as gentle during this descent and will appear to be struggling with it&#8217;s own prop wash, I have actually successfully tested this descent speed without any issues. It will reduce the time necessary from 100 m / 328  ft to 10 m / 33 ft from previously 60 s to now **36 seconds**.

Next we eliminate the RTL loiter time (<a href="http://ardupilot.org/copter/docs/parameters.html#RTL_loiter_time_ArduCopterRTL_LOIT_TIME" target="_blank">RTL_LOIT_TIME</a>) altogether. Again, this is an emergency event and we therefore rather want IRIS to descent a bit more harsh from 10 m / 33 ft altitude than run out of juice and crash into pieces.

Last but not least we will also increase the Land speed (<a href="http://ardupilot.org/copter/docs/parameters.html#Land_speed_ArduCopterLAND_SPEED" target="_blank">LAND_SPEED</a>) from 0.5 m /s to 0.66 m / s (or 66 cm / s). This will decrease the final descent from 20s to **15.2 seconds** for this part of the descent.

With the tuned settings we can therefore bring IRIS safely to the ground from 100 m / 328 ft in 36s + 15.2s = 51.2 seconds. That is less than 1 minute.

In the above flight with the battery failsafe voltage remaining at 10.5V the LiPo voltage would still have been at 10.2V at this point and the Lipo would not have been damaged.

**Improvements in ArduCopter code**

While it looks like we are done here, there are certainly some improvements that could go into ArduCopter based on the above lessons learned. Keep in mind that the above settings will now also affect a regular RTL or LAND event, one which was not triggered by a failsafe. That&#8217;s not necessarily what we want.

This becomes even more obvious for the case of Loiter Horizontal Maximum Speed (<a href="http://ardupilot.org/copter/docs/parameters.html#Loiter_Horizontal_Maximum_Speed_WPNAV_LOIT_SPEED" target="_blank">WPNAV_LOIT_SPEED</a>) and Waypoint Acceleration (<a href="http://ardupilot.org/copter/docs/parameters.html#Waypoint_Acceleration_WPNAV_ACCEL" target="_blank">WPNAV_ACCEL</a>). These values area applied to regular missions, used for e.g. photography, recording videos or capturing aerial images. In all of these cases we do not want to fly with the maximum possible speed of IRIS. Yet in a battery failsafe event we might want to rush at maximum speed from our location over water to the launch point.

Treating a battery failsafe as an emergency event during which we are willing to push the limits would call for having a dedicated FS\_RTL and FS\_LAND mode, where we can configure above settings specific to these modes. E.g. via something like FS\_WPNAV\_SPEED\_DN, FS\_RTL\_LOIT\_TIME or FS\_LAND\_SPEED.

And while we are at it with possible improvements: Arducopter knows the distance from the current location to the launch point and it knows how many mAh IRIS has been using in average per minute. How about stringing all this knowledge together with a bit of math and initiating a RTL failsafe just in time to make it home before the battery drops below 20%. A second LAND failsafe could kick in for the current altitude to make it to the ground based on the configured FS\_WPNAV\_SPEED\_DN, FS\_RTL\_LOIT\_TIME and FS\_LAND\_SPEED as well as the current altitude and remaining mAh.

But an even simpler step would be a multi-stage battery failsafe. At stage 1, configurable via voltage level or remaining mAh, the operator would be warned, e.g. via LED and sound along with a message on the GCS. At stage 2, configurable similar to stage 1, IRIS would initiate a RTL mission and stage 3, initiating a LAND mission.

&nbsp;

&nbsp;
