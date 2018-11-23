---
id: 142
title: Mounting the IRIS Telemetry antenna differently
date: 2014-09-20T16:25:15+00:00
author: Christian Elsen
layout: post
permalink: /2014/09/20/mounting-the-iris-telemetry-antenna-differently/
image: /content/uploads/2014/09/2014-09-19-21-02-51-672x372.jpg
thumbnail: /content/uploads/2014/09/2014-09-19-21-02-51-150x150.jpg
categories:
  - 3DR IRIS
  - Telemetry
tags:
  - fix
  - telemetry
---
In a [previous post](https://www.cloud-surfer.net/2014/07/25/protecting-the-iris-telemetry-antenna-against-damage/ "Protecting the IRIS Telemetry antenna against damage") I already wrote about the problem with the the default antenna mount position of IRIS. If you actually look carefully, you&#8217;ll notice three problems:

  * When flipping over IRIS during a crash landing you can easily damage the antenna and/or Telemetry module
  * You cannot un-/tighten the antenna without removing the top hull
  * The antenna is directly connected to the transmitter board, passing through any physical tension and stress from the antenna to the board

These problems are all solved in the IRIS+, as the antenna is now located towards the side of the top hull, points downwards and is connected to the transmitter board via a cable (See Figure 1).

<div id="attachment_143" style="width: 310px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/3drobotics-iris-drone-14178.jpg"><img class="size-medium wp-image-143" src="/content/uploads//2014/09/3drobotics-iris-drone-14178.jpg?w=300" alt="Figure 1: 3DR IRIS+ with new Telemetry antenna location" width="300" height="200" srcset="/content/uploads/2014/09/3drobotics-iris-drone-14178.jpg 900w, /content/uploads/2014/09/3drobotics-iris-drone-14178-300x200.jpg 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

  <p class="wp-caption-text">
    Figure 1: 3DR IRIS+ with new Telemetry antenna location
  </p>
</div>

Unfortunately the IRIS-to-IRIS+ upgrade kit does not provide the material to move the antenna location of your existing IRIS. In this post I will show you, how you can easily relocate your IRIS transmitter antenna and thereby fix at least two of the three problems very easily.

**Required materials and tools**

  * Small <a href="http://amzn.to/2eFdsq6" target="_blank">stripes of 3M Dual Lock Reclosable Fastener</a> or a <a href="http://amzn.to/2eFddLu" target="_blank">large roll of it</a>
  * (Optional) [RP-SMA Male to Female Right Angle 90-Degree Adapter](http://amzn.to/2eiQf1k)

**How-to assemble**

After opening the top hull of IRIS, follow below steps to relocate your Telemetry module:

  * Unscrew the three small plastic screws that hold the Telemetry module onto the plastic spacers
  * Remove at least the rear plastic spacer
  * Tape a stripe of 3M Dual Lock on the bottom of the Telemetry module
  * Tape another stripe of 3M Dual Lock on the top shell, a little further to the back of where the Telemetry module used to be located (See Figure 2). <div id="attachment_144" style="width: 310px" class="wp-caption aligncenter">
      <a href="/content/uploads/2014/09/2014-09-19-21-03-24.jpg"><img class="size-medium wp-image-144" src="/content/uploads/2014/09/2014-09-19-21-03-24.jpg?w=300" alt="Figure 2: Telemetry module attached with 3M Dual Lock" width="300" height="168" srcset="/content/uploads/2014/09/2014-09-19-21-03-24.jpg 3264w, /content/uploads/2014/09/2014-09-19-21-03-24-300x168.jpg 300w, /content/uploads/2014/09/2014-09-19-21-03-24-1024x576.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

      <p class="wp-caption-text">
        Figure 2: Telemetry module attached with 3M Dual Lock
      </p>
    </div>

    Make sure that you place the 3M Dual Lock, so that with the Telemetry module attached the following is possible:

      * The locations is not too far to the right. You can still close the top hull.
      * The locations is sufficiently towards the back. You can point the antenna downwards and you can un-/tighten the antenna without removing the shell.
      * The Telemetry module does not touch the Pixhawk! This is very crucial, as you will otherwise introduce vibrations
  * Close the top shell again

As a result you will be able to point the Telemetry antenna downwards and also un-/tighten the antenna (See Figure 3).

<div id="attachment_145" style="width: 178px" class="wp-caption aligncenter">
  <a href="/content/uploads/2014/09/2014-09-19-21-02-51.jpg"><img class="size-medium wp-image-145" src="/content/uploads/2014/09/2014-09-19-21-02-51.jpg?w=168" alt="Figure 3: Telemetry antenna pointing down on IRIS" width="168" height="300" srcset="/content/uploads/2014/09/2014-09-19-21-02-51.jpg 1836w, /content/uploads/2014/09/2014-09-19-21-02-51-168x300.jpg 168w, /content/uploads/2014/09/2014-09-19-21-02-51-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

  <p class="wp-caption-text">
    Figure 3: Telemetry antenna pointing down on IRIS
  </p>
</div>

In this position the antenna will block easy access to the battery door. For improved usability place a 90 degree angled RP-SMA adapter between the Telemetry module and the antenna, pointing the base of the antenna out to the right side.

&nbsp;
