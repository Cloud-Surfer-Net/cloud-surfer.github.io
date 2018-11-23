---
id: 71
title: Get rid of Jello with the Tarot T-2D gimbal
date: 2014-07-11T09:59:02+00:00
author: Christian Elsen
layout: post
permalink: /2014/07/11/get-rid-of-jello-with-the-tarot-t-2d-gimbal/
image: /wp-content/uploads/2014/07/motorscreen.png
thumbnail: /content/uploads/2014/07/motorscreen-150x150.png
categories:
  - 3DR IRIS
  - Gimbal
tags:
  - fix
---
Have you noticed Jello in your video while using the Tarot T-2D gimbal. Here the Jello is not coming from vibrations due to the motors or props, but the gimbal itself. Even with IRIS on the ground and motors turned off, you can sometimes see the vibrations of the camera and the resulting Jello in the video footage. In this article I will show you how to fix this.

**Required materials and tools**

The following materials are required.

  * The USB dongle and cable that came with your Tarot T-2D Gimbal
  * A charged battery for your IRIS

The following tools are required:

  * None

**How-to assemble**

Follow these steps to change the configuration of the Gimbal motor settings:

  * (Optional) It is highly recommended to <a href="http://ardupilot.org/copter/docs/common-tarot-gimbal.html#Updating_the_gimbal_software" target="_blank">upgrade</a> the Gimbal software to the latest version.
  * Use the provided USB dongle to connect the Gimbal board to your computer (Windows only). You have to connect to the _motor driver connector_ (See below).

    <img src="/content/uploads/2014/07/gimbal_pixhawk_tarot-300x177.png" alt="" width="300" height="177" class="aligncenter size-medium wp-image-72" srcset="/content/uploads/2014/07/gimbal_pixhawk_tarot-300x177.png 300w, /content/uploads/2014/07/gimbal_pixhawk_tarot-1024x606.png 1024w, /content/uploads/2014/07/gimbal_pixhawk_tarot.png 1115w" sizes="(max-width: 300px) 100vw, 300px" />
  * Download and unzip the <a href="http://ardupilot.org/?did=110" target="_blank">Tarot Gimbal Firmware v1.5 zip</a> file to a convenient place on your computer.
  * Double click on the ZYX-BMGC-EN_V1.5.exe file (found in the above zip) and the configuration UI shown below should appear.

    <img src="/content/uploads/2014/07/mainconfig-300x220.png" alt="" width="300" height="220" class="aligncenter size-medium wp-image-74" srcset="/content/uploads/2014/07/mainconfig-300x220.png 300w, /content/uploads/2014/07/mainconfig.png 889w" sizes="(max-width: 300px) 100vw, 300px" />
  * Click on the _Motor Configuration_ button in the lower center of the screen and the configuration UI shown below should appear.

    <img src="/content/uploads/2014/07/motorscreen-300x191.png" alt="" width="300" height="191" class="aligncenter size-medium wp-image-75" srcset="/content/uploads/2014/07/motorscreen-300x191.png 300w, /content/uploads/2014/07/motorscreen.png 580w" sizes="(max-width: 300px) 100vw, 300px" />
  * Power the Gimbal by plugging in the battery of your IRIS.
  * In the configuration UI, select the COM port and press the “Open COM Port” button.  After a few seconds you should see the values for _Rolling Motor_ and _Tilting Motor_ to be updated.
  * Change the value for _Tilting motor -> Power_ to the value _25_.
  * Save the settings to the Tarot gimbal by clicking on _Write Settings to Flash_.
  * You can now disconnect the USB dongle and power cycle IRIS.

**Results**

As a result vibrations of the Tarot Gimbal should stop and the Jello from your video footage should be gone.
