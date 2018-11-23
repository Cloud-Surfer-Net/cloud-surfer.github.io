---
id: 152
title: FPV setup for IRIS
date: 2014-09-28T16:46:20+00:00
author: Christian Elsen
layout: post
permalink: /2014/09/28/fpv-setup-for-iris/
image: /content/uploads/2014/09/finalsetup-672x372.jpg
thumbnail: /content/uploads/2014/09/finalsetup-150x150.jpg
categories:
  - 3DR IRIS
  - FPV
tags:
  - fpv
---
Unfortunately 3DR does not offer a dedicated FPV kit for IRIS and the FPV kits available from 3rd parties do not include an On-Screen-Display (OSD). Therefore here the instruction on how to assemble your own FPV kit &#8211; no soldering required.

**Addressed design Requirements**

But before we get started, let&#8217;s go over some design requirements. These are the requirements that I wanted to fulfill with my IRIS FPV setup:

  * **Weight:** The setup &#8211; especially the transmitter &#8211; should be small and lightweight as IRIS is already under-powered as is.
  * **Power-Source:** The setup should use the main battery as power source, as adding another battery would increase the weight of IRIS even more.
  * **OSD:** The setup should include an OSD (On-Screen-Display) module for receiving flight data, while in flight. It is almost impossible to judge your altitude or speed from looking solely at the video feed. Having such critical information displayed right in front of you helps a lot. Even though you can use an Android enabled tablet to receive flight data, having redundancy of these information improves flight safety. Also when using goggles as the ground segment of your FPV setup, having important flight information directly displayed in front of your eyes is crucial.
  * **Camera:** The setup will use the GoPro camera attached to the Gimbal or mounted on the front as the camera. An additional camera would yet again add weight to IRIS. (While the usage of a GoPro as FPV camera is discussed controversially in various forums, I haven&#8217;t had any issues in 100+ flights with the GoPro locking up or freezing, other than user error. See below for more.)
  * **Accessibility:** It should be possible to access the Transmitter in order to change channels without having to open the top hull.
  * **5.8GHz channels: **The setup should work with all available channels in the 5.8 GHz band and not just the F band used by Fatshark.

    In addition the setup will only include the air part. You are free to use whatever ground part you like. Both goggles or screen will work just fine.
  * **Soldering:** No soldering required: Myself I&#8217;m neither willing nor capable to solder anything on IRIS. Therefore I wanted an FPV solution that does not require soldering. If you are willing and capable to solder, you can e.g. solder the power cables together instead of using the JST Plug 1 Female to 2 Male Expansion Adapter below.
  * **Turn On/Off:** The user should be able to decide before each flight whether to use the FPV setup or not. When e.g. flying an auto mapping mission with the GoPro setup for taking pictures, the FPV can be safely disabled.
  * **Battery voltage:** The setup should work with both 3S and 4S batteries.
  * **Power GoPro Camera:** (Optional) It should be possible to power the GoPro from the IRIS main battery. The reason for doing so is the following: The GoPro camera will stop video output via the USB-like port after a few minutes, unless it is powered or recording. Therefore in case you fly FPV with a GoPro camera and without external power and forget to hit the record button, you might suddenly get a black screen mid flight. Believe me, not a great situation. Been there, done that.

With these goals in mind, let&#8217;s get started

**Required materials and tools**

You will need the following materials:

  * <a href="http://www.getfpv.com/5-8ghz-32ch-a-v-500mw-transmitter-ts58500.html" target="_blank">Boscam 5.8GHz 32CH A/V 500mW Transmitter</a>
  * <a href="http://www.getfpv.com/ibcrazy-5-8-ghz-bluebeam-ultra-antenna-set.html" target="_blank">IBCrazy 5.8 GHz Bluebeam Ultra Antenna Set<br /> </a>(While other &#8211; cheaper &#8211; antennas, such as the included dipole, would also work, the quality of the antenna is more crucial than the wattage of the transmitter. Therefore don&#8217;t be cheap on the antenna!)
  * <a href="http://www.getfpv.com/filtered-balance-lead-power-supply.html" target="_blank">FatShark Filtered Balance Lead Power Supply 2s-4s</a>
  * <a href="http://www.getfpv.com/lc-common-mode-power-filter.html" target="_blank">LC Common Mode Power Filter<br /> </a>(Even though the FatShark Balance Lead claims to be filtered, it is not sufficient to suppress interference from the noisy ESCs. You definitely want this Filter!)
  * <a href="http://www.ebay.com/itm/360938363634" target="_blank">MAVLink-OSD On-Screen Display Board MinimOSD V1.2 APM Telemetry to APM2.5 2.6<br /> </a>(The MAVLink OSD module requires 5V power on the digital side and 5-12V power on the analog side. This would require a very complicated power harness. Instead one can connect the power source for digital and analog side with a solder point and power the OSD via the Pixhawk. Unfortunately 3DR doesn&#8217;t offer the possibility to purchase an OSD module that already has the solder points set. If you are not able or willing to solder, you therefore need to purchase an OSD module that already has the solder point set. The above clone available on eBay does have the solder points set.)
  * <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=9631&aff=1269428" target="_blank">JST Female 2 pin connector set (10pcs/set)</a>
  * <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=9630&aff=1269428" target="_blank">JST Male 2 pin connector set (10pcs/set)</a>
  * <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=29277&aff=1269428" target="_blank">JWT connectors, 1 pin &#8211; 5set/bag</a>
  * Tarot Gimbal GoPro Video Cable
  * MinimOSD cable for Pixhawk
  * (Optional) FTDI Cable 3.3V

    (This cable is used to configure the OSD module. It will allow you to decide what flight data is displayed during the flight)
  * Small <a href="http://amzn.to/2eFdsq6" target="_blank">stripes of 3M Dual Lock Reclosable Fastener</a> or a <a href="http://amzn.to/2eFddLu" target="_blank">large roll of it</a>

If you want to power the GoPro camera from the main flight battery of IRIS you will also need these materials:

  * <a href="http://www.ebay.com/itm/331103817064" target="_blank">JST Plug 1 Female to 2 Male Expansion Adapter<br /> </a>
  * Servo Extension Cable Male-Female &#8211; 15cm
  * <a href="http://www.ebay.com/itm/400699597933" target="_blank">3A Switching UBEC Input 2-6 Lipo Output 5V 3A</a>

The following tools are required:

  * <a href="http://amzn.to/2eiQf1k" target="_blank">SainSmart Dupont Pin Crimping Tool</a>
  * Wire stripper
  * Scissors

**Warnings!**

Please read these important warnings carefully!

  * _Never_ power on the Boscam FPV Transmitter without an 5.8 GHz antenna attached to it! It will permanently damage your FPV Transmitter.
  * The use and operation of FPV transmitter in the USA and many other countries may require a license and some countries may forbid its use entirely. In the USA, you will need a &#8220;HAM&#8221; amateur radio license. It is your responsibility to ensure that the use of these instructions and product meets the requirements imposed by your government’s rules and regulations for RF devices!

**How-to assemble**

Let&#8217;s get started assembling our FPV setup.

**Step 1: Changing connectors**

First we will need to change a few connectors on the cables:

  * On the cable that comes with the Boscam 5.8GHz 32CH A/V 500mW Transmitter, cut off the USB adapter as close to the adapter as possible (See Figure 1).
    <div id="attachment_156" style="width: 310px" class="wp-caption aligncenter">
      <a href="/content/uploads/2014/09/fpv-tx-cable.png"><img class="size-medium wp-image-156" src="/content/uploads/2014/09/fpv-tx-cable.png?w=300" alt="Figure 1: Remove the USB adapter" width="300" height="300" srcset="/content/uploads/2014/09/fpv-tx-cable.png 1000w, /content/uploads/2014/09/fpv-tx-cable-150x150.png 150w, /content/uploads/2014/09/fpv-tx-cable-300x300.png 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

      <p class="wp-caption-text">
        Figure 1: Remove the USB adapter
      </p>
    </div></li>

      * Use the Pin Crimping Tool and place JWT connectors (1 pin) onto each of the two wires. We will later use these two connectors to connect to the Video Out/Ground of the OSD module (See Figure 2).
        <div id="attachment_157" style="width: 307px" class="wp-caption aligncenter">
          <a href="/content/uploads/2014/09/fpv-tx-changed-cable.jpg"><img class="size-medium wp-image-157" src="/content/uploads/2014/09/fpv-tx-changed-cable.jpg?w=297" alt="Figure 2: OSD module connected to FPV TX" width="297" height="300" srcset="/content/uploads/2014/09/fpv-tx-changed-cable.jpg 1360w, /content/uploads/2014/09/fpv-tx-changed-cable-297x300.jpg 297w, /content/uploads/2014/09/fpv-tx-changed-cable-1015x1024.jpg 1015w" sizes="(max-width: 297px) 100vw, 297px" /></a>

          <p class="wp-caption-text">
            Figure 2: OSD module connected to FPV TX
          </p>
        </div></li>

          * Next, on the FatShark Filtered Balance Lead Power Supply cut off one of the molex plugs (See Figure 3).
            <div id="attachment_165" style="width: 310px" class="wp-caption aligncenter">
              <a href="/content/uploads/2014/09/fatshark-cable.png"><img class="size-medium wp-image-165" src="/content/uploads/2014/09/fatshark-cable.png?w=300" alt="Figure 3: Fatshark Cable with connector to be replace" width="300" height="214" srcset="/content/uploads/2014/09/fatshark-cable.png 578w, /content/uploads/2014/09/fatshark-cable-300x214.png 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

              <p class="wp-caption-text">
                Figure 3: Fatshark Cable with connector to be replace
              </p>
            </div></li>

              * Use the Pin Crimping Tool and replace it with a JST Male 2 pin connector (See Figure 4). Pay attention to the polarity (red and black wire)! Refer to the picture below for correct polarity.
                <div id="attachment_158" style="width: 310px" class="wp-caption aligncenter">
                  <a href="/content/uploads/2014/09/jst-male.png"><img class="wp-image-158 size-medium" src="/content/uploads/2014/09/jst-male.png?w=300" alt="Figure 4: JST Male connector" width="300" height="289" srcset="/content/uploads/2014/09/jst-male.png 384w, /content/uploads/2014/09/jst-male-300x289.png 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                  <p class="wp-caption-text">
                    Figure 4: JST Male connector
                  </p>
                </div></li> </ul>

                If you want to power your GoPro via the main flight battery, you also need to change the following cables:

                  *  On the open end of the 5V / 3A Switching UBEC install a JST Female 2 pin connector (See Figure 5). Pay attention to the polarity (red and black wire)! Refer to the picture below for correct polarity. <div id="attachment_159" style="width: 307px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/jst-female.png"><img class="wp-image-159 size-medium" src="/content/uploads/2014/09/jst-female.png?w=297" alt="Figure 5: JST Female connector" width="297" height="300" srcset="/content/uploads/2014/09/jst-female.png 384w, /content/uploads/2014/09/jst-female-297x300.png 297w" sizes="(max-width: 297px) 100vw, 297px" /></a>

                      <p class="wp-caption-text">
                        Figure 5: JST Female connector
                      </p>
                    </div>

                    &nbsp;</li> </ul>

                    **Step 2: Install the components**

                    Next, let&#8217;s install the needed components. We will start with the FPV transmitter.

                    Use a small strip of 3M Dual Lock on the back of the FPV transmitter &#8211; the side that does not include the switches for the channels and the connector. Use the corresponding 3M Dual Lock strip on the bottom of the lower IRIS shell, between Gimbal and battery door (See Figure 6). Carefully cut free the connector and channel switches through the plastic wrap of the FPV transmitter.

                    <div id="attachment_167" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/fpv-tx.jpg"><img class="wp-image-167 size-medium" src="/content/uploads/2014/09/fpv-tx.jpg?w=300" alt="Figure 6: FPV transmitter mounted with 3M Dual Lock" width="300" height="168" srcset="/content/uploads/2014/09/fpv-tx.jpg 3264w, /content/uploads/2014/09/fpv-tx-300x168.jpg 300w, /content/uploads/2014/09/fpv-tx-1024x576.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                      <p class="wp-caption-text">
                        Figure 6: FPV transmitter mounted with 3M Dual Lock
                      </p>
                    </div>

                    Point the connector of the FPV transmitter towards the Gimbal. Attach the air side of the IBCrazy 5.8 GHz Bluebeam Ultra Antenna via the included angled adapter to the FPV transmitter. The antenna should point downwards for optimum transmission.

                    Use some more 3M Dual Lock to attach the OSD module, LC Common Mode Power Filter and optional 3A Switching UBEC to the top plate, underneath the top hull. Place all these components right in front of the Pixhawk, while ensuring that they do not touch the Pixhawk (See Figure 7).

                    <div id="attachment_168" style="width: 178px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/top-plate-modules.jpg"><img class="size-medium wp-image-168" src="/content/uploads/2014/09/top-plate-modules.jpg?w=168" alt="Figure 7: FPV components mounted on top plate" width="168" height="300" srcset="/content/uploads/2014/09/top-plate-modules.jpg 1836w, /content/uploads/2014/09/top-plate-modules-168x300.jpg 168w, /content/uploads/2014/09/top-plate-modules-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

                      <p class="wp-caption-text">
                        Figure 7: FPV components mounted on top plate
                      </p>
                    </div>

                    Point the analog side (field with 3&#215;2 connectors) towards the right middle. That&#8217;s where will later route the cables to.

                    **Step 3: Routing the cables**

                    Route the Tarot Gimbal GoPro Video Cable in parallel to the existing Tarot Gimbal control cable. You will need to temporarily remove the lower shell for this. Make sure that any excess length of the cable is towards the Gimbal. Plug the USB end of the cable into the GoPro camera (See Figure 8). Ensure that the Gimbal can still freely move and that you can tilt the camera without any problems.

                    <div id="attachment_169" style="width: 178px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/gimbal-usb.jpg"><img class="size-medium wp-image-169" src="/content/uploads/2014/09/gimbal-usb.jpg?w=168" alt="Figure 8: Cable connected to GoPro USB port" width="168" height="300" srcset="/content/uploads/2014/09/gimbal-usb.jpg 2448w, /content/uploads/2014/09/gimbal-usb-168x300.jpg 168w, /content/uploads/2014/09/gimbal-usb-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

                      <p class="wp-caption-text">
                        Figure 8: Cable connected to GoPro USB port
                      </p>
                    </div>

                    Connect the Tarot Gimbal GoPro Video Cable to the OSD module. Use the plug, where the wires run to the outer connectors and the middle connector is unused (See Figure 9). The opening of the connector with the metal pins has to face upwards onto the top 3&#215;1 row of the 3&#215;2 connector field.

                    <div id="attachment_170" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/gopro-pin-out.jpg"><img class="size-medium wp-image-170" src="/content/uploads/2014/09/gopro-pin-out.jpg?w=300" alt="Figure 9: Connect Tarot Gimbal GoPro Video Cable to OSD module" width="300" height="152" srcset="/content/uploads/2014/09/gopro-pin-out.jpg 3394w, /content/uploads/2014/09/gopro-pin-out-300x152.jpg 300w, /content/uploads/2014/09/gopro-pin-out-1024x519.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                      <p class="wp-caption-text">
                        Figure 9: Connect Tarot Gimbal GoPro Video Cable to OSD module
                      </p>
                    </div>

                    Next connect the FPV Transmitter cable &#8211; the one where we replace the USB plug with a JWT connector &#8211; to the OSD module (See Figure 10). The cable with the white line on it will need to connect to the Video Out pin on the 3&#215;2 field and the black cable will need to connect to the Ground pin on the 3&#215;2 field. Route this cable along the two Gimbal cables towards the FPV transmitter on the bottom of IRIS.

                    <div id="attachment_171" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/osd-to-fpv-tx.jpg"><img class="size-medium wp-image-171" src="/content/uploads/2014/09/osd-to-fpv-tx.jpg?w=300" alt="Figure 10: OSD module connected to FPV TX" width="300" height="172" srcset="/content/uploads/2014/09/osd-to-fpv-tx.jpg 5104w, /content/uploads/2014/09/osd-to-fpv-tx-300x172.jpg 300w, /content/uploads/2014/09/osd-to-fpv-tx-1024x589.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                      <p class="wp-caption-text">
                        Figure 10: OSD module connected to FPV TX
                      </p>
                    </div>

                    If you are using the 3A Switching UBEC, connect the Servo Extension Cable to the remaining connector of the Tarot Gimbal GoPro Video Cable. You should notice that the black and red wires of the Servo Extension Cable match up to the two black cables of the Tarot Gimbal GoPro Video Cable, the white wire is not used.

                    Plug the other end of the Servo Extension Cable into the back of the Pixhawk. Use the port &#8220;Main Out #8&#8221;, with the black wire on the top pin and the white wire on the bottom pin (See Figure 11).

                    <div id="attachment_172" style="width: 178px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/pixhawk-connection.jpg"><img class="size-medium wp-image-172" src="/content/uploads/2014/09/pixhawk-connection.jpg?w=168" alt="Figure 10: Powering the Pixhawk via the 5V UBEC" width="168" height="300" srcset="/content/uploads/2014/09/pixhawk-connection.jpg 1836w, /content/uploads/2014/09/pixhawk-connection-168x300.jpg 168w, /content/uploads/2014/09/pixhawk-connection-576x1024.jpg 576w" sizes="(max-width: 168px) 100vw, 168px" /></a>

                      <p class="wp-caption-text">
                        Figure 10: Powering the Pixhawk via the 5V UBEC
                      </p>
                    </div>

                    Connect the Output of the 5V / 3A UBEC to port &#8220;Main Out #5, with the black wire on the top pin and the red wired on the middle pin.

                    This will power the Pixhawk via the 5V / 3A UBEC in addition to the previous power source. It will also provide the power for the GoPro via the Servo Extension Cable.

                    Next place the FatShark Filtered Balance Lead Power Supply into the back of the battery bay and route the cable between the lower tray and the lower shell towards the right side of IRIS and up to the upper shell (See Figure 11).

                    <div id="attachment_173" style="width: 178px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/fatshark-power.jpg"><img class="size-medium wp-image-173" src="/content/uploads/2014/09/fatshark-power.jpg?w=168" alt="Figure 11: FatShark Filtered Balance Lead Power Supply" width="168" height="300" /></a>

                      <p class="wp-caption-text">
                        Figure 11: FatShark Filtered Balance Lead Power Supply
                      </p>
                    </div>

                    With the MinimOSD cable for Pixhawk connect the port &#8220;Telem2&#8221; on the Pixhawk to the OSD module. The metal pins on the plug of the OSD module site have to face downwards (See Figure 12).

                    <div id="attachment_174" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/telemcable.jpg"><img class="size-medium wp-image-174" src="/content/uploads/2014/09/telemcable.jpg?w=300" alt="Figure 11: MinimOSD cable for Pixhawk" width="300" height="224" /></a>

                      <p class="wp-caption-text">
                        Figure 11: MinimOSD cable for Pixhawk
                      </p>
                    </div>

                    **Step 4: Add power cables for the components**

                    This steps depends on whether you want to power the GoPro camera with the 5V / 3A UBEC or not.

                    Let&#8217;s start with the case that you don&#8217;t: In this case, connect the FatShark Filtered Balance Lead to the LC Common Mode Power Filter. From the LC Common Mode Power Filter connect directly to the Boscam 5.8 GHz FPV transmitter (See Figure 12).

                    <div id="attachment_175" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/power1.jpg"><img class="size-medium wp-image-175" src="/content/uploads/2014/09/power1.jpg?w=300" alt="Figure 12: Power setup without 5V / 3A UBEC" width="300" height="120" srcset="/content/uploads/2014/09/power1.jpg 311w, /content/uploads/2014/09/power1-300x120.jpg 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                      <p class="wp-caption-text">
                        Figure 12: Power setup without 5V / 3A UBEC
                      </p>
                    </div>

                    In case you do want to use a 5V / 3A UBEC: Connect the FatShark Filtered Balance Lead to the JST Plug 1 Female to 2 Male Expansion Adapter. From one output of the expansion adapter connect to the LC Common Mode Power Filter. From the LC Common Mode Power Filter connect directly to the Boscam 5.8 GHz FPV transmitter. From the other output of the expansion adapter connect to the 5V / 3A UBEC (See Figure 13).

                    <div id="attachment_176" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/power2.jpg"><img class="size-medium wp-image-176" src="/content/uploads/2014/09/power2.jpg?w=300" alt="Figure 13: Power setup with 5V / 3A UBEC" width="300" height="146" srcset="/content/uploads/2014/09/power2.jpg 444w, /content/uploads/2014/09/power2-300x146.jpg 300w" sizes="(max-width: 300px) 100vw, 300px" /></a>

                      <p class="wp-caption-text">
                        Figure 13: Power setup with 5V / 3A UBEC
                      </p>
                    </div>

                    **Step 5: Configuring the Pixhawk**

                    Before you can use the OSD module, the Pixhawk has to be configured for transmitting Telemetry data to the OSD module. Use Mission Planner to change the following <a href="http://ardupilot.org/copter/docs/parameters.html" target="_blank">ArduCopter parameters</a>.

                    This is the complete list with the respective values:

                      * SERIAL2_BAUD, 57 (telemetry output at 57600)
                      * SR2\_EXT\_STAT, 2 ( 2hz for waypoints, GPS raw, fence data, current waypoint, etc)
                      * SR2_EXTRA1, 5 ( 5hz for attitude and simulation state)
                      * SR2\_EXTRA2, 2 ( 2hz for VFR\_Hud data )
                      * SR2_EXTRA3, 3 ( 3hz for AHRS, Hardware Status, Wind )
                      * SR2_POSITION, 2 ( 2hz for location data )
                      * SR2\_RAW\_SENS, 2 ( 2hz for raw imu sensor data )
                      * SR2\_RC\_CHAN, 5 ( 5hz for radio input or radio output data )
                      * BRD\_SER2\_RTSCTS, 0 ( Disable Request to Send / Clear to Send )

                    **Step 6: Using your FPV setup**

                    When you are ready to use your FPV setup with IRIS, follow this sequence to power up IRIS and the FPV equipment:

                      1. Power up your FPV receiver, e.g. <a href="http://amzn.to/2etdOnt" target="_blank">FatShark goggles</a> or the excellent <a href="http://amzn.to/2eb7wWq" target="_blank">FlySight screen with build-in receiver</a>.

                        Don&#8217;t forget to check out my [FPV ground station setup](https://www.cloud-surfer.net/2015/03/22/fpv-ground-station/ "FPV Ground Station").
                      2. Power up your GoPro camera.
                      3. Connect the main battery lead to IRIS. This will power up IRIS the same ways as before. It will not power the FPV transmitter though.
                      4. Connect the balance lead of the battery to the FatShark Filtered Balanced Lead. Within a few seconds you should see the output of the GoPro camera and the OSD module booting.

                        Sometimes the OSD module becomes stuck in the boot process and you will not see any Telemetry data. In that case, disconnect both balance lead and main lead and start again from Step #2.

                    During flights you should see update telemetry information overlayed by the OSD module on top of your GoPro video (See Figure 14).

                    <div id="attachment_177" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/fpv-screen.jpg"><img class="size-medium wp-image-177" src="/content/uploads/2014/09/fpv-screen.jpg?w=300" alt="Figure 14: Example of FPV output" width="300" height="168" /></a>

                      <p class="wp-caption-text">
                        Figure 14: Example of FPV output
                      </p>
                    </div>

                    After a flight, disconnect both the main battery lead as well as the balance lead. This is especially important for the case that you use the 5V / 3A UBEC. With this setup the Pixhawk will be powered by this UBEC for the case that the main power source via the main battery lead fails. As a result it will initiate a battery failsafe after 5 secs, as it detects the voltage to be 0V.

                    **Configuring your OSD**

                    You can configure the layout of the OSD screen, in order to declutter it and only display the information important to you. For this you will need the <a href="https://code.google.com/archive/p/arducam-osd/wikis/OSD_Config_Tool.wiki" target="_blank">OSD Config Tool</a> as well as the FTDI Cable 3.3V.

                    Use the same cable and software to <a href="https://code.google.com/archive/p/arducam-osd/wikis/Cfg_Update_Firmware.wiki" target="_blank">update the MinimOSD software</a> and <a href="https://code.google.com/archive/p/arducam-osd/wikis/Cfg_Update_CharSet.wiki" target="_blank">charset</a>.

                    **Downloading media from the GoPro**

                    In a previous post, I already provided a <a title="Angled Mini-SUB adapter for GoPro in Tarot Gimbal" href="https://www.cloud-surfer.net/2014/07/11/mini-usb-adapter-for-tarot-gimbal/" target="_blank">solution for connecting to the GoPro USB port</a> without removing the camera from the Gimbal. Unfortunately this approach won&#8217;t work anymore, as the Tarot Gimbal GoPro Video Cable cannot connect via the <a href="http://amzn.to/2eFegv3" target="_blank">Motorola Right Angle Charger Adapter</a>. The solution is to carefully cut off the black rubber casing around the Motorola Right Angle Charger adapter.

                    This will allow you to unplug the Tarot Gimbal GoPro Video Cable and plug in the Motorola Right Angle Charger adapter, while the GoPro remains in the Gimbal (See Figure 15).

                    <div id="attachment_178" style="width: 310px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/motorola-cable.jpg"><img class="size-medium wp-image-178" src="/content/uploads/2014/09/motorola-cable.jpg?w=300" alt="Figure 15: Angled Mini-USB adapter with removed rubber casing" width="300" height="168" /></a>

                      <p class="wp-caption-text">
                        Figure 15: Angled Mini-USB adapter with removed rubber casing
                      </p>
                    </div>

                    **Final Setup**

                    The final setup from the outside is visible in Figure 16.

                    <div id="attachment_186" style="width: 178px" class="wp-caption aligncenter">
                      <a href="/content/uploads/2014/09/finalsetup.jpg"><img class="size-medium wp-image-186" src="/content/uploads/2014/09/finalsetup.jpg?w=168" alt="Figure 16: Final FPV setup" width="168" height="300" /></a>

                      <p class="wp-caption-text">
                        Figure 16: Final FPV setup
                      </p>
                    </div>

                    Flight time reduction due to the FPV setup is marginal. Range of the setup exceeds by far the R/C range of IRIS.

                    **Alternatives**

                    The presented FPV solution does provide a lot of options for alternatives. In case your design requirements differ from the ones listed above, feel free to alterrate the setup accordingly. Here are some ideas:

                      * If you don&#8217;t need support for 4S Lipos, but only want to use 3S Lipos, you can replace the FatShark Filtered Balance Lead with <a href="http://www.ebay.com/itm/161389116561" target="_blank">3S Lipo JST-XH to Male JST Camera Gimbal Adapter</a>.
                      * If you don&#8217;t want the option to not use the FPV setup during each flight, you could either purchase another <a href="http://www.ebay.com/itm/331103817064" target="_blank">JST Plug 1 Female to 2 Male Expansion Adapter</a> and embed it between IRIS and the Tarot Gimbal.

                        Or you could solder a <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=9682&aff=1269428" target="_blank">Male JST battery pigtail 10cm length (10pcs/bag)</a> to IRIS.
                      * If you are on a budget or have to use a less powerful FPV transmitter due to local regulations, you can also use the <a href="http://www.hobbyking.com/hobbyking/store/uh_viewitem.asp?idproduct=63114&aff=1269428" target="_blank">SkyZone TS5823 5.8GHz 32CH A/V 200mW Mini FPV Transmitter (v2)</a>. Note that this transmitter uses a RP-SMA connector. You therefore need to purchase a <a href="http://www.ebay.com/itm/RP-SMA-male-to-SMA-female-Right-Angle-RF-connector-Adapter-Fast-Handling-/111286345740" target="_blank">RP-SMA male to SMA female Right Angle RF connector</a>.

                    **Updates for IRIS+**

                    IRIS+ already uses the Telem2 port on the Pixhawk for providing telemetry data via the R/C transmitter. This port is configured for the FrSky Telemetry protocol, which is different from the Mavlink protocol used for the MimimOSD or the 3DR Telemetry radio. Therefore a special Y cable &#8211; similar to this Telemetry/OSD Y-cable adapter cable for APM 2.6 and 3DR Radio V2 &#8211; has to be made for the Pixhawk. This cable will need to connect the Telem1 port with both the 3DR Telemetry radio and the MimimOSD. Such a cable does not exists as a readymade option today.

                    An alternative would be to not use the Telem2 for the R/C transmitter telemetry and use the above instructions. reconfiguring it for Mavlink usage with MinimOSD. In this case you will not have telemetry data on the R/C transmitter.
