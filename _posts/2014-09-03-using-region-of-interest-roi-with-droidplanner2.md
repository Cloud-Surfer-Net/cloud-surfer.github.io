---
id: 127
title: Using Region of Interest (ROI) with DroidPlanner2
date: 2014-09-03T15:42:05+00:00
author: Christian Elsen
layout: post
permalink: /2014/09/03/using-region-of-interest-roi-with-droidplanner2/
redirect_from: 
  - /2014/09/03/using-region-of-interest-roi-with-droidplanner2/amp/
image: /content/uploads/2014/09/screenshot_2014-09-02-20-50-06-672x372.png
thumbnail: /content/uploads/2014/09/screenshot_2014-09-02-20-50-06-150x150.png
categories:
  - DroidPlanner / 3DR Tower
  - Ground Control Station
tags:
  - auto mission
  - droidplanner2
  - ROI
---
The waypoint type Region of Interest (ROI) points the nose of the vehicle and camera gimbal at the “region of interest”. Let&#8217;s have a look at how to use it with <a href="https://play.google.com/store/apps/details?id=org.droidplanner&hl=en" target="_blank" rel="nofollow">DroidPlanner2</a>.

**Required software and version**

The current version (as of September 3rd, 2014) of DroidPlanner2 as available on <a href="https://play.google.com/store/apps/details?id=org.droidplanner&hl=en" target="_blank" rel="nofollow">Google Play</a>, does not yet support the ROI waypoint feature. You need to download and install one of the latest beta versions.

As of this writing I recommend to use version <a href="https://github.com/DroidPlanner/Tower/releases/tag/Droidplanner_v2.6.2_RC1" target="_blank">Droidplanner v2.6.2 RC1</a>, which can be downloaded as an apk file.

**How-to use**

After opening Droidplanner2 on your Android table or phone, change to the Edit mode.

You will notice that Droidplanner2 already has a default waypoint with the #1 defined. This is a waypoint of type &#8220;take-off&#8221;.

Let&#8217;s add a second waypoint to where you want your region of interest to be placed (See Figure 1).

<div id="attachment_130" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-48-05.png"><img class="size-medium wp-image-130" src="/content/uploads/2014/09/screenshot_2014-09-02-20-48-05.png?w=300" alt="Figure 1: Drop Waypoint as ROI" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-48-05.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-05-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-05-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 1: Drop Waypoint as ROI
  </p>
</div>

Next draw your desired flight path around the ROI (See Figure 2).

<div id="attachment_131" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-48-23.png"><img class="size-medium wp-image-131" src="/content/uploads/2014/09/screenshot_2014-09-02-20-48-23.png?w=300" alt="Figure 2: Draw line for flight path" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-48-23.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-23-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-23-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 2: Draw line for flight path
  </p>
</div>

Now select the waypoint you want to become the ROI. In this case it&#8217;s waypoint #2 (See Figure 3).

<div id="attachment_132" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-48-32.png"><img class="size-medium wp-image-132" src="/content/uploads/2014/09/screenshot_2014-09-02-20-48-32.png?w=300" alt="Figure 3: Select waypoint, you want to become the ROI" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-48-32.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-32-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-32-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 3: Select waypoint, you want to become the ROI
  </p>
</div>

As the waypoint type chose &#8220;Region of Interest&#8221; (See Figure 4). The altitude specified within the Region of Interest is the altitude of the target. During execution of the mission, IRIS will not only point the nose (and thereby the camera) towards this target, but also adjust the tilt of the Gimbal (if available) to keep the camera pointed at the correct height of the target.

<div id="attachment_133" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-48-43.png"><img class="size-medium wp-image-133" src="/content/uploads/2014/09/screenshot_2014-09-02-20-48-43.png?w=300" alt="Figure 4: Select &quot;Region of Interest&quot; as waypoint type" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-48-43.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-43-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-48-43-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 4: Select &#8220;Region of Interest&#8221; as waypoint type
  </p>
</div>

(Optional) Next add another waypoint of type &#8220;Land&#8221; in order to land your quadcopter (See Figure 5).

<div id="attachment_128" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-49-16.png"><img class="size-medium wp-image-128" src="/content/uploads/2014/09/screenshot_2014-09-02-20-49-16.png?w=300" alt="Figure 5: Set waypoint to land the quad" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-49-16.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-49-16-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-49-16-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 5: Set waypoint to land the quad
  </p>
</div>

Send the planned mission to your quadcopter. It&#8217;s ready for execution now.

**Executing the mission**

But before we execute this mission, let&#8217;s walk through what will happen during this Auto Mission (See Figure 6).

<div id="attachment_129" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-02-20-50-06.png"><img class="size-medium wp-image-129" src="/content/uploads/2014/09/screenshot_2014-09-02-20-50-06.png?w=300" alt="Figure 6: Auto Mission with Region of Interest" width="300" height="187" srcset="/content/uploads/2014/09/screenshot_2014-09-02-20-50-06.png 1280w, /content/uploads/2014/09/screenshot_2014-09-02-20-50-06-300x187.png 300w, /content/uploads/2014/09/screenshot_2014-09-02-20-50-06-1024x640.png 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 6: Auto Mission with Region of Interest
  </p>
</div>

  * Waypoint #1: First the quad will take off and ascent straight up to the configured height. Here this height is 10m.
  * Waypoint #2: Next the quad will position itself with the nose pointing towards the region of interest (ROI) waypoint and adjust the Gimbal tilt angle to match the ROI height (in this case 0m).
  * Waypoint #3: Now the quad will fly towards the location of waypoint #3, while still pointing the nose towards the ROI and adjusting the Gimbal angle to match the ROI height. It will also climb up to the configured height (here 20m).
  * Waypoint #4 and following: What happens now depends on which version of ArduCopter you&#8217;re using:
      * With ArduCopter 3.1, the quad will point towards waypoint #4 and reset the Gimbal angle, after reaching waypoint #3. It will continue thereafter the flight, pointing the nose of the quad towards the waypoint that it&#8217;s flying towards to.
      * With ArduCopter 3.2, the quad will keep pointing towards the ROI, while flying along all remaining waypoints (in this case #7).
  * Waypoint #8: The quad will fly towards waypoint #8. Once it reached the location, it will decent and effectively land. The Gimbal tilt angle will return to the position it was before the mission.
