---
id: 241
title: Offline maps with DroidPlanner / 3DR Tower
date: 2014-09-30T15:11:14+00:00
author: Christian Elsen
layout: post
permalink: /2014/09/30/offline-maps-with-droidplanner/
image: /content/uploads/2014/09/screenshot_2014-09-29-22-58-01-672x372.png
thumbnail: /content/uploads/2014/09/screenshot_2014-09-29-22-58-01-150x150.png
categories:
  - DroidPlanner / 3DR Tower
  - Ground Control Station
tags:
  - droidplanner2
  - maps
  - tower
---
A <a href="http://amzn.to/2dyurrQ" target="_blank">Nexus 7 tablet</a> is an excellent choice as the Ground Control Station (GCS) with <a href="https://play.google.com/store/apps/details?id=org.droidplanner&hl=en" target="_blank" rel="nofollow">DroidPlanner2</a> or <a href="https://play.google.com/store/apps/details?id=org.droidplanner.android&hl=en" target="_blank" rel="nofollow">3DR Tower</a> for your IRIS or other quadcopter. But in order to keep costs in a reasonable manner, using the Wifi-only model makes a lot of sense. Yet, doing so one wants to still use maps in DroidPlanner2 while being out in the field.

DroidPlanner2 and 3DR Tower already offers map caching via the Google Maps API out of the box. If a user zooms the map somewhere while connected to Wifi, disconnects from Wifi, closes the app, reloads the app, it will still show you the map area from before. But DroidPlanner2 doesn&#8217;t have control on how much of the area is cached. You might end up with the desired map area not being cached, showing you either a blurry map or a blank map.

To overcome this shortcoming you will need the offline map feature of DroidPlanner2 and 3DR Tower, which stores map tiles in a special folder for DroidPlanner2 and 3DR Tower to be used. This allows you to be sure that the map area that you need is always available while the Android device has no network connectivity.

In this post I&#8217;ll show you, how you can use the offline map feature in DroidPlanner2 and 3DR Tower to accomplish exactly this: Be out in the field without network connectivity and have your maps available.

**Note:** I recommend to place your Nexus 7 or any other tablet into flight mode &#8211; thus disabling any radio module in it &#8211; during flight operations. Especially as I have [mounted the GCS very close to the R/C transmitter](https://www.cloud-surfer.net/2014/07/10/tablet-mount-for-iris-radio/ "Tablet mount for IRIS radio"), this reduces the risk of radio interference on the 2.4 GHz band between the WiFi module of the Nexus 7 and the R/C transmitter.

**Required software and version**

  * DroidPlanner2: The current version of DroidPlanner2, available on <a href="https://play.google.com/store/apps/details?id=org.droidplanner&hl=en" target="_blank" rel="nofollow">Google Play</a>, does support usage of Offline Maps.

    or <a href="https://play.google.com/store/apps/details?id=org.droidplanner.android&hl=en" target="_blank" rel="nofollow">Tower (DroidPlanner 3)</a>, which requires <a href="https://play.google.com/store/apps/details?id=org.droidplanner.services.android&hl=en" target="_blank" rel="nofollow">3DR Services</a> as well.
  * Mission Planner: The latest version of <a href="http://ardupilot.org/?did=82" target="_blank">Mission Planner</a> is available from the APM Download section.
  * A file manager for Android, such as &#8220;File Manager (Explorer)&#8221;, available on <a href="https://play.google.com/store/apps/details?id=com.rhmsoft.fm" target="_blank">Google Play</a>.

**How-to use**

First we need to assemble the offline maps in Mission Planner on the PC. For this open Mission Planner and change to the Flight Plan tab. Zoom in or out to the area for which you want to create an offline map.

Hold down the &#8220;Alt&#8221; button on your keyboard and draw a box around the area that you desire for your offline maps (See Figure 1).

<div id="attachment_192" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/capture01.png"><img class="size-medium wp-image-192" src="/content/uploads/2014/09/capture01.png?w=300" alt="Figure 1: Draw the map area  on the flight plan screen" width="300" height="215" /></a>

  <p class="wp-caption-text">
    Figure 1: Draw the map area on the flight plan screen
  </p>
</div>

Next zoom in to the level at which you want the offline maps to be captured. Then perform a right-click in the map area and select Map Tool -> Prefetch (See Figure 2) to start the map ripping.

<div id="attachment_193" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/capture02.png"><img class="size-medium wp-image-193" src="/content/uploads/2014/09/capture02.png?w=300" alt="Figure 2: Chose Map Tool -> Prefetch" width="300" height="215" /></a>

  <p class="wp-caption-text">
    Figure 2: Chose Map Tool -> Prefetch
  </p>
</div>

Confirm the zoom level at which you want to start the map ripping with a click on the &#8220;Yes&#8221; button.

<div id="attachment_194" style="width: 273px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/capture03.png"><img class="size-full wp-image-194" src="/content/uploads/2014/09/capture03.png" alt="Figure 3: Confirm the zoom level " width="263" height="146" /></a>

  <p class="wp-caption-text">
    Figure 3: Confirm the zoom level
  </p>
</div>

Wait for the map titles to be fetched (ripped). Mission Planner will try to ripp the maps beyond the zoom level that you previously defined. Once the zoom level displayed is higher than your desired zoom level, press the &#8220;ESC&#8221; button twice quickly (See Figure 4). This will end the map fetching and save you time.

<div id="attachment_195" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/capture04.png"><img class="size-medium wp-image-195" src="/content/uploads/2014/09/capture04.png?w=300" alt="Figure 4: Mission Planner fetching map tiles" width="300" height="55" /></a>

  <p class="wp-caption-text">
    Figure 4: Mission Planner fetching map tiles
  </p>
</div>

Navigate to the map file folder _%ProgramFiles(x86)%Mission PlannergmapcacheTileDBv3enGoogleSatelliteMap_ on a 64-bit system or _%ProgramFiles%Mission PlannergmapcacheTileDBv3enGoogleSatelliteMap_ on a 32-bit system (See Figure 5). If you were using a different provider of maps in Mission Planner, other than the Google Satellite Maps, navigate to the corresponding folder. In this folder you&#8217;ll notice subfolders, which correspond to the zoom levels. Delete the folders that have a higher number than the zoom level that you desire. Compact the remaining folders and all their content into a single Zip file, called e.g. &#8220;maps.zip&#8221;. Copy this file to your Android tablet, e.g. using <a href="https://drive.google.com/" target="_blank">Google Drive</a>.

<div id="attachment_196" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/capture05.png"><img class="size-medium wp-image-196" src="/content/uploads/2014/09/capture05.png?w=300" alt="Figure 5: Map Tiles downloaded  in the map cache folder" width="300" height="155" /></a>

  <p class="wp-caption-text">
    Figure 5: Map Tiles downloaded in the map cache folder
  </p>
</div>

&nbsp;

On your Android tablet, use a File Manager and navigate to the folder _/storage/emulated/0/DroidPlanner/Maps_. Unzip the previously created Zip file into this folder. This should create the numbered subfolders and their content (See Figure 6).

With Tower (Droidplanner 3) this folder is called _/storage/emulated/0/Tower/Maps instead._

Create an empty file named &#8220;.nomedia&#8221; inside the _/storage/emulated/0/DroidPlanner/Maps_ or _/storage/emulated/0/Tower/Maps _folder._ _This will prevent Android to treat the map images and media and will not show them in your Images application.

<div id="attachment_197" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-29-22-56-57.png"><img class="size-medium wp-image-197" src="/content/uploads/2014/09/screenshot_2014-09-29-22-56-57.png?w=300" alt="Figure 6: DroidPlanner2 offline map folder in Android File Manager" width="300" height="187" /></a>

  <p class="wp-caption-text">
    Figure 6: DroidPlanner2 offline map folder in Android File Manager
  </p>
</div>

Next open DroidPlanner2 or 3DR Tower and navigate to the User Preferences screen under Settings. Tap on the Map Provider Preferences (See Figure 7).

<div id="attachment_198" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-29-22-57-31.png"><img class="size-medium wp-image-198" src="/content/uploads/2014/09/screenshot_2014-09-29-22-57-31.png?w=300" alt="Figure 7: Maps section in the User Preferences screen" width="300" height="187" /></a>

  <p class="wp-caption-text">
    Figure 7: Maps section in the User Preferences screen
  </p>
</div>

Set the tick box next to &#8220;Use offline maps&#8221; (See Figure 8).

<div id="attachment_199" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-29-22-57-40.png"><img class="size-medium wp-image-199" src="/content/uploads/2014/09/screenshot_2014-09-29-22-57-40.png?w=300" alt="Figure 8: Tickbox for &quot;Use Offline Maps&quot;" width="300" height="187" /></a>

  <p class="wp-caption-text">
    Figure 8: Tickbox for &#8220;Use Offline Maps&#8221;
  </p>
</div>

Return to the Flight Data screen. You will see offline maps available, even when disabling the WiFi connectivity.

<div id="attachment_200" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/screenshot_2014-09-29-22-58-01.png"><img class="size-medium wp-image-200" src="/content/uploads/2014/09/screenshot_2014-09-29-22-58-01.png?w=300" alt="Figure 9: DroidPlanner2 with offline maps displayed" width="300" height="187" /></a>

  <p class="wp-caption-text">
    Figure 9: DroidPlanner2 with offline maps displayed
  </p>
</div>

It would be great if DroidPlanner2 or 3DR Tower itself had the ability to define a map area and download the map tiles, while connected to a WiFi network. This would safe users from the hassle of having to use Mission Planner.
