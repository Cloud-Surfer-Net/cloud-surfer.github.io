---
id: 321
title: Enabling Extended Kalman filter (EKF) on IRIS+
date: 2015-05-04T19:20:58+00:00
author: Christian Elsen
layout: post
permalink: /2015/05/04/enabling-extended-kalman-filter-ekf-on-iris/
redirect_from: 
  - /2015/05/04/enabling-extended-kalman-filter-ekf-on-iris/amp/
image: /content/uploads/2015/05/EKF_Enable_02.png
thumbnail: /content/uploads/2015/05/EKF_Enable_02-e1438903708540-142x150.png
categories:
  - 3DR IRIS
  - Sensors
tags:
  - parameters
---
IRIS+ runs the opens-oruce flight control software <a href="http://ardupilot.org/" target="_blank">APM:Copter</a>. With <a href="http://diydrones.com/profiles/blogs/arducopter-3-2-ready-for-wider-use" target="_blank">version 3.2</a> &#8211; which was released on November 7th, 2014 &#8211; an interesting new feature was introduced: <a href="https://en.wikipedia.org/wiki/Extended_Kalman_filter" target="_blank">Extended Kalman filter</a> (EKF).

On your IRIS+ the EKF  uses rate gyroscopes, accelerometer, magnetometer, GPS and barometric pressure measurements to estimate the position, velocity and angular orientation of the flight vehicle. Taking all these sensor values into consideration at the same time allows the EKF to reject measurements of an individual sensor with significant errors. This way IRIS+ becomes less susceptible to faults that affect a single sensor, such as an accelerometer.

Unfortunately this feature is not turned on by default in version 3.2 of APM:Copter. But it is very easy to do so, if you are already using Droidplanner or 3DR Tower on your Android tablet as a Ground Control Station (GCS).

**Required software and version**

  * DroidPlanner / Tower: The current version of <a href="https://play.google.com/store/apps/details?id=org.droidplanner&hl=en" target="_blank" rel="nofollow">DroidPlanner2</a>, available on Google Play or <a href="https://play.google.com/store/apps/details?id=org.droidplanner.android&hl=en" target="_blank" rel="nofollow">Tower</a> (DroidPlanner 3), which requires <a href="https://play.google.com/store/apps/details?id=org.droidplanner.services.android&hl=en" target="_blank" rel="nofollow">3DR Services</a> as well.

**How-to use**

Power-up your IRIS and your Android tablet, then connect Droidplanner or 3DR Tower to IRIS+ via the wireless radio. This is basically the same procedure as getting ready to fly with your GCS.

There is no need to arm IRIS.

Open the &#8220;Menu&#8221; and select &#8220;Parameters&#8221; (See Figure 1).

<div id="attachment_339" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2015/05/EKF_Enable_01.png"><img src="/content/uploads/2015/05/EKF_Enable_01-300x187.png" alt="Figure 1: Parameters screen" width="300" height="187" class="size-medium wp-image-339" srcset="/content/uploads/2015/05/EKF_Enable_01-300x187.png 300w, /content/uploads/2015/05/EKF_Enable_01-1024x639.png 1024w, /content/uploads/2015/05/EKF_Enable_01-100x62.png 100w, /content/uploads/2015/05/EKF_Enable_01-150x94.png 150w, /content/uploads/2015/05/EKF_Enable_01-200x125.png 200w, /content/uploads/2015/05/EKF_Enable_01-450x281.png 450w, /content/uploads/2015/05/EKF_Enable_01-600x374.png 600w, /content/uploads/2015/05/EKF_Enable_01-900x561.png 900w, /content/uploads/2015/05/EKF_Enable_01.png 1283w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 1: Parameters screen
  </p>
</div>

Droidplanner / 3DR Tower will load the current APM:Copter parameters from your IRIS. This can take a few seconds.

In the list of parameters, scroll down until you find the entry &#8220;AHRS\_EKF\_USE&#8221;, which should have a value of &#8220;0&#8221; by default. Tap on the value &#8220;0&#8221; and change it to &#8220;1&#8221; (See Figure 2).

<div id="attachment_328" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2015/05/EKF_Enable_02.png"><img src="/content/uploads/2015/05/EKF_Enable_02-300x187.png" alt="Figure 2: Change AHRS_EKF_USE parameter to 1" width="300" height="187" class="size-medium wp-image-328" srcset="/content/uploads/2015/05/EKF_Enable_02-300x187.png 300w, /content/uploads/2015/05/EKF_Enable_02-1024x637.png 1024w, /content/uploads/2015/05/EKF_Enable_02-100x62.png 100w, /content/uploads/2015/05/EKF_Enable_02-150x93.png 150w, /content/uploads/2015/05/EKF_Enable_02-200x124.png 200w, /content/uploads/2015/05/EKF_Enable_02-450x280.png 450w, /content/uploads/2015/05/EKF_Enable_02-600x373.png 600w, /content/uploads/2015/05/EKF_Enable_02-900x560.png 900w, /content/uploads/2015/05/EKF_Enable_02.png 1286w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 2: Change AHRS_EKF_USE parameter to 1
  </p>
</div>

Now save your changed to IRIS parameter by tapping in the upper right corner on the three dots and then choosing &#8220;Upload Parameters&#8221; (See Figure 3) and power cycle IRIS.

<div id="attachment_334" style="width: 231px" class="wp-caption aligncenter">
  <a href="/content/uploads/2015/05/EKF_Enable_03.png"><img src="/content/uploads/2015/05/EKF_Enable_03-221x300.png" alt="Figure 3: Upload Parameters" width="221" height="300" class="size-medium wp-image-334" srcset="/content/uploads/2015/05/EKF_Enable_03-221x300.png 221w, /content/uploads/2015/05/EKF_Enable_03-100x136.png 100w, /content/uploads/2015/05/EKF_Enable_03-150x204.png 150w, /content/uploads/2015/05/EKF_Enable_03-200x271.png 200w, /content/uploads/2015/05/EKF_Enable_03-300x407.png 300w, /content/uploads/2015/05/EKF_Enable_03-450x611.png 450w, /content/uploads/2015/05/EKF_Enable_03.png 554w" sizes="(max-width: 221px) 100vw, 221px" /></a>

  <p class="wp-caption-text">
    Figure 3: Upload Parameters
  </p>
</div>

That&#8217;s it. Now your IRIS will use EKF, making it less susceptible to faults that affect a single sensor, such as an accelerometer.
