---
id: 97
title: 'Copper shield for IRIS&#8217; GPS module'
date: 2014-07-14T16:54:10+00:00
author: Christian Elsen
layout: post
permalink: /2014/07/14/copper-shield-for-iris-gps-module/
image: /content/uploads/2014/07/gps-shield-installed1.jpg
thumbnail: /content/uploads/2014/07/gps-shield-installed1-150x150.jpg
categories:
  - 3DR IRIS
  - Sensors
tags:
  - fix
  - gps
---
Various folks in the IRIS forums at <a href="http://diydrones.com/group/iris" target="_blank">DIYDronres</a>, <a href="http://ardupilot.org/?f=48" target="_blank">Ardupilot</a>, and the <a href="https://www.facebook.com/groups/635611993176188/" target="_blank">IRIS Facebook group</a> have complained about poor GPS performance on their IRIS. Others (including myself) weren&#8217;t quite sure if there was something wrong with their GPS module, but weren&#8217;t quite stunned with the performance either. So I decide to shield my GPS module with a piece of copper shield and find out what difference it makes.

**Required materials and tools**

The following materials are required.

  * <a href="https://www.amazon.com/gp/product/B008U0LNNU/ref=as_li_tl?ie=UTF8&camp=1789&creative=390957&creativeASIN=B008U0LNNU&linkCode=as2&tag=cloudsurfer-20&linkId=L6T63WLM5P76DXXA" target="_blank">WD Copper Shielding Foil 8&#8243; X 12&#8243;</a>
  * A piece of paper
  * Scotch tape

The following tools are required:

  * Pair of scissors

**How-to assemble**

Follow these steps to assemble your copper shield for IRIS:

  * Out of the WD Copper Shielding Foil cut a square of the size 8 cm x 8 cm / 3 in. x 3 in. Do not remove the paper from the tape side.
  * Cut a piece of paper of the exact same size as the WD Copper Shielding Foil.
  * Place the piece of paper on the shiny side of the WD Copper Shielding Foil.
  * Use scotch tape around the edges of the piece of paper and the WD Copper Shielding Foil to tape the two together.

    You should receive a &#8220;sandwich&#8221; of paper &#8211; copper &#8211; paper with scotch tape all around the edges.
  * <a href="https://3dr.com/wp-content/uploads/2014/02/removing-the-shell.pdf" target="_blank">Open the top hull</a> of your IRIS.
  * Place your copper foil &#8220;sandwich&#8221; over the GPS module. Affix it to the hull with scotch tape (See Figure 1). <div id="attachment_98" style="width: 310px" class="wp-caption aligncenter">
      <a href="/content/uploads/2014/07/gps-shield-installed.jpg"><img class="size-medium wp-image-98" src="/content/uploads/2014/07/gps-shield-installed.jpg?w=300" alt="Figure 1: Copper shield over GPS module" width="300" height="168" srcset="/content/uploads/2014/07/gps-shield-installed.jpg 2113w, /content/uploads/2014/07/gps-shield-installed-300x168.jpg 300w, /content/uploads/2014/07/gps-shield-installed-1024x576.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

      <p class="wp-caption-text">
        Figure 1: Copper shield over GPS module
      </p>
    </div>

    &nbsp;</li>

      * Make sure that the antennas from the FrSky R/C transmitter are not underneath the copper shield.

        If necessary move them to the side of the copper shield.

        **Note:** The FrSky R/C can cause interference with the GPS module. Thus part of this fix includes ensuring that the antennas of the R/C module are away from the GPS receiver.</ul>

    **Results**

    Now the big question: Does it make a difference? To answer this question I performed two test flights: One with the copper shield in place and right afterwards another one with the copper shield removed. Here are the results:

      *  **Flight 1: Copper Shield in place** <div id="attachment_99" style="width: 615px" class="wp-caption aligncenter">
          <a href="/content/uploads/2014/07/gps_coverage_with.png"><img class="wp-image-99 size-large" src="/content/uploads/2014/07/gps_coverage_with.png?w=605" alt="Figure 2: GPS coverage with GPS shield in place" width="605" height="140" srcset="/content/uploads/2014/07/gps_coverage_with.png 1366w, /content/uploads/2014/07/gps_coverage_with-300x69.png 300w, /content/uploads/2014/07/gps_coverage_with-1024x238.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

          <p class="wp-caption-text">
            Figure 2: GPS coverage with GPS shield in place
          </p>
        </div>

        After the warm start of the GPS, the horizontal <a href="https://en.wikipedia.org/wiki/Dilution_of_precision_(GPS)" target="_blank">dilution of precision</a> (HDOP) goes down to ~1.3 and the number of visible satellites is around 13-14.</li>

          * **Flight 2: Copper Shield Removed** <div id="attachment_100" style="width: 615px" class="wp-caption aligncenter">
              <a href="/content/uploads/2014/07/gps_coverage_without.png"><img class="size-large wp-image-100" src="/content/uploads/2014/07/gps_coverage_without.png?w=605" alt="Figure 3: GPS coverage without GPS shield in place" width="605" height="140" srcset="/content/uploads/2014/07/gps_coverage_without.png 1366w, /content/uploads/2014/07/gps_coverage_without-300x69.png 300w, /content/uploads/2014/07/gps_coverage_without-1024x238.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

              <p class="wp-caption-text">
                Figure 3: GPS coverage without GPS shield in place
              </p>
            </div>

            Here the HDOP varies between 1.4 and 2.4. The number of satellites available is around 10-11.</li> </ul>

            Looking at the <a href="http://satpredictor.navcomtech.com/" target="_blank" rel="nofollow">Satellite Prediction website</a> for the date and location when the tests were performed, we can see that the number of available satellites is between 12 and 14 at 16:50 – 17:20 GMT.

            <div id="attachment_101" style="width: 615px" class="wp-caption aligncenter">
              <a href="/content/uploads/2014/07/sat_prediction.png"><img class="size-large wp-image-101" src="/content/uploads/2014/07/sat_prediction.png?w=605" alt="Figure 4: Satellite prediction for tests" width="605" height="200" srcset="/content/uploads/2014/07/sat_prediction.png 1291w, /content/uploads/2014/07/sat_prediction-300x99.png 300w, /content/uploads/2014/07/sat_prediction-1024x338.png 1024w" sizes="(max-width: 605px) 100vw, 605px" /></a>

              <p class="wp-caption-text">
                Figure 4: Satellite prediction for tests
              </p>
            </div>

            After looking at these results, I did put the copper shield back in. The difference in HDOP and number of visible satellites might be small, but it did make a difference for me. And the cost and effort for this fix was minimal.

            Since applying the fix I have not have had any satellite coverage issues (e.g. in Loiter mode) and time to first acquisition is very fast.

            &nbsp;
