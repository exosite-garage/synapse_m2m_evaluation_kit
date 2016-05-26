<p><span class="wysiwyg-font-size-x-large">Overview </span></p>
<p>Exosite has worked with Synapse Wireless to create an evaluation kit based on Synapse's SNAP Connect E10 Gateway.  This E10 Gateway has an Ethernet connection and runs Linux in addition to internally having a SNAP RF Engine embedded in it so act as a gateway for a SNAP network to the internet.</p>
<p>The evaluation kit is made up of a Synapse SNAPConnect E10 <em>Gateway</em> and two Synapse RF Engines running on protoboards in addition to some external sensors and LEDs.  The software for this evaluation kit can be used for any make-up of devices and is meant as an evaluation tool and reference code for your specific M2M and Internet of Thing projects.  </p>
<p><img src="/hc/en-us/article_attachments/200184784/exo_gw_synapse_eval_kit_graphics1.png" alt="" /></p>
<p> </p>
<p> </p>
<p><span class="wysiwyg-font-size-x-large">Getting Started</span></p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-large"><strong>Wiring up your RF Engine Protoboards</strong></span></span></p>
<p>Please wire up your RF Engine protoboards per this graphic.  The pre-installed SNAP application script (SNAPpy) expects the protoboards to be connected to these sensors and LEDs.  This kit includes a Red and Green LEDs, a Photo Cell sensor and a Thermistor sensor for measuring temperature.</p>
<p><em>Note: The LEDs have a positive and negative side, there should be a slight flat edge on the negative side of the LED in addition to the negative lead being shorter.</em>  </p>
<p> </p>
<p><img class="wysiwyg-text-align-center" src="/hc/en-us/article_attachments/200249020/synapse_eval_kit_rf100Proto_hookup1.png" alt="" width="522" height="505" /></p>
<p>For more details on this hook-up information, please see the EK2100 User Guide, Holiday Light Show demo section.  The only diffence is there is only a Red and Green LED, placing the green LED where the yellow is in the user guide.  </p>
<p><a href="http://www.synapse-wireless.com/documents/products/Synapse-EK2100-Starter-Kit-User-Guide.pdf">EK2100 User Guide</a></p>
<p> </p>
<p> </p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-large"><strong>Add your devices to Exosite Web Portal</strong></span></span></p>
<ol>
<li>Go to <strong><a style="background-color: #ffffff;" href="https://synapse.exosite.com" target="_blank">https://synapse.exosite.com</a></strong> and log-in or create a new account.</li>
<li>Once you are logged in, click '<strong>Add a Device</strong>' on the Menu on the left-hand side. <img src="/hc/en-us/article_attachments/200226154/home_page_no_devices1.png" alt="" /></li>
<li>On the Add Device Menu, Pick <em><strong>Exosite Evaluation SNAP E10 Gateway Kit v1</strong></em> and click continue.  Enter the MAC Address of your E10 which can be found on the bottom sticker of the unit, provide a name for your device and an optional location, hit Continue. <img src="/hc/en-us/article_attachments/200129959/adding_device1.png" alt="" width="519" height="444" /> </li>
<li>Your E10 Gateway has now been added to your account.  You can now add your SNAP RF Engine Nodes the same way, except choose <em><strong>Exosite Evaluation SNAP Node Protoboard v1</strong></em> for the device type when adding the devices.</li>
</ol>
<p style="padding-left: 30px;">After adding your gateway and two nodes, your home page will look something like this.  If you click on any of the devices, you'll see the default application dashboard.</p>
<p><img src="/hc/en-us/article_attachments/200129949/home_page_steps.png" alt="" /> </p>
<p> </p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-large"><strong>Power On and Connect Your Hardware</strong></span></span></p>
<p style="padding-left: 30px;"><font size="2">The Synapse gateway and nodes are pre-programmed with application code that will attempt to send data to Exosite.  There are a couple of steps to making this happen.  The first step is that the Gateway and the Nodes must 'pair'. This is so the nodes can direct their wireless function calls to a specific gateway which then intern communicates to Exosite.  </font></p>
<p style="padding-left: 30px;"><font size="2">The second essential step is that the gateway and the nodes provision with Exosite using their unique identifier (MAC Address, SNAP address).  Only one user can 'own' a device.</font></p>
<ol>
<li><span style="font-size: small;">Power on your E10 Gateway by either using the included USB Power plug or connecting the USB cable to your computer.  When connecting to your computer, this USB connection can provide you with a Serial port to see the Linux console for the E10 providing debug information.  <strong>LEDB</strong> should turn green right away and the Ethernet connector LEDs should be blinking.<img src="/hc/en-us/article_attachments/200196545/e10_hook-up.png" alt="" /></span></li>
<li><span style="font-size: small;">Power on your RF Engine nodes.  <strong>Board LED1 should be blinking once per second</strong> if the node does not have a 'paired' gateway address stored in non-volatile memory.</span></li>
<li><span style="font-size: small;">To 'pair' your nodes to your gateway, press and hold the <strong>'mode' button</strong> of your E10 until <strong>LED A</strong> blinks red once per second.  (It is usually green).  The E10 is now in 'paring mode'.  LED A and the Mode button are on the Antenna side of the E10.<img src="/hc/en-us/article_attachments/200196595/e10_node_pairing.png" alt="" /></span></li>
<li><span style="font-size: small;">The nodes will automatically attempt to pair every <strong>5 seconds</strong> if they have not been paired to an E10 Gateway.  <em>Note: To easily 'clear' a paired gateway address on a node, you can hold in the button on the prototype board when powering on the node, any paired gateway stored in non-volatile memory will be erased and the device will try to find a new E10 to pair with.</em></span></li>
<li><span style="font-size: small;">When a node has paired to an E10 gateway, it will flash <strong>LED2 once per second</strong> until it has provisioned with Exosite.  Once a node has paired and activated, it will blink <strong>LED1 and LED2 together once every two seconds</strong>.</span></li>
<li><span style="font-size: small;">If the E10 has a good network connection and is able to connect to Exosite, it will 'Activate' and begin sending data to the Exosite Portal.  It will also attemp to activate for each node that has paired to it.  <em>Note: An E10 will not activate until a user adds the E10 to their portal, nor be able to activate (provision) a node to Exosite.</em></span></li>
<li><span style="font-size: small;">Once the gateway and nodes have activated and started sending data, they will show up as 'active' on your home page. (Green icon)</span></li>
</ol>
<p><font size="2"> </font></p>
<p><em><font size="2">Note: This act of 'pairing' nodes to a gateway is specific to the reference application code for this kit, both on the nodes and the E10 gateway.  Developers are able to choose how they would want nodes and gateways to talk together using Synapse's SNAP application code once they begin developing on their own.  For the ease of use for this kit, this approach was chosen to make sure nodes could be paired to a specific E10 and lessen the chance a node would pair to another E10 in the same local area.  </font></em></p>
<p> </p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-large"><strong>Using the Default Application</strong></span></span></p>
<p><img src="/hc/en-us/article_attachments/200134089/home_page_kits_active1.png" alt="" width="548" height="350" /></p>
<p><span class="wysiwyg-font-size-medium wysiwyg-font-size-large" style="font-size: small;">Once your devices have been added and they've started sending data, you can click on the devices in the Device List on your home page.  This will bring up the default application dashboard for that device.  The SNAP RF Engines show graphs for their RF signal, Temperature sensor value, Photo Sensor value, and push button activity.  You can also remotely turn on/off the Red and Green LEDs that have been added.</span></p>
<p><img src="/hc/en-us/article_attachments/200249200/node_application_dashboard1.png" alt="" width="516" height="511" /> </p>
<p><strong><span class="wysiwyg-font-size-large"> </span></strong></p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-medium"><strong>LED Control</strong></span></span></p>
<p><span class="wysiwyg-font-size-medium"><em>Demonstrates reading from Exosite</em></span></p>
<p>Clicking on the On/Off buttons on the default application dashboard will result in the nodes turning the connected Red and Green LEDs on and off.  This is an example of showing remote control and sending instructions to a remote node.  In this case, the SNAP Node has requested these two data sourced to be 'polled' by the E10 gateway every 2 seconds.  Check out the SNAP Node application code to see how this works.</p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-medium"><strong>Push Button logging</strong></span></span></p>
<p><em><span class="wysiwyg-font-size-medium">Demonstrates writing to Exosite</span></em></p>
<p>When a user pushes the button on the Protoboard, the SNAP application sends a SNAP RPC request to the E10 to write a value to the push button data source.  The default application dashboard shows a log of these values with their time-stamp.  This demonstrates a interrupt on the SNAP Node causing a data write to Exosite.</p>
<p><span class="wysiwyg-underline"><span class="wysiwyg-font-size-medium"><strong>Temperature, Photo Cell , Signal Strength</strong></span></span></p>
<p><em><span class="wysiwyg-font-size-medium">Demonstrates writing to Exosite and Exosite scripting</span></em></p>
<p>The SNAP node application has a time triggered loop in which it sends signal strength in -dBm, temperature as an analog A/D input value (in bits), and a photo-cell value in a range of 0 to 100 (percentage) converted on the node from an A/D input value.  </p>
<p>The signal is graphed exactly as is.  The Photocell range value and the analog temperature value are sent as a JSON formated string so that two pieces of information can be sent at one time.  This JSON string looks something like this: <em>{"atmp":519,"ph":17}</em> to a data source in Exosite called 'packet'.  There is an Exosite script that then parses this value and puts the individual values into specific data sources.  This demonstrates how an <a href="/en-us/articles/200513440-Scripting">Exosite script</a> can be used for parsing data.</p>
<p>The analog Temperature value also has a script associated with it.  This script takes the analog value and converts it to degrees F and stores it into another data source.  This shows how Exosite scripts can be used to process data.</p>
<p><a href="/en-us/articles/200513440-Scripting">Exosite Scripting</a></p>
<p> </p>
<p><span class="wysiwyg-underline wysiwyg-font-size-large"><strong>Customizing</strong></span></p>
<p>Users can build custom dashboards, create their own widgets, create new scripts, and add other data from the nodes using the Exosite web portal tool.  To edit the RF Engine SNAP application on the nodes, Exosite provides the SNAPpy script.  Please see below.</p>
<p><a href="/hc/en-us/categories/200035036-Portals-Web-Portal-Dashboard-Interface">Exosite Portals documentation</a> - Dashboards, Widgets, and other features of the web tool</p>
<p><a href="/hc/en-us/articles/200513440-Scripting">Exosite Scripting</a> - API and overview of Exosite's platform scripting</p>
<p><a href="/hc/en-us/articles/200455293-API-documentation-Libraries">Exosite's APIs</a> - Links to Exosite's platform's APIs </p>
<p><a href="http://www.synapse-wireless.com/snap">Synapse SNAP Reference</a></p>
<p><a href="http://www.synapse-wireless.com/snap-components-free-developers-IDE-tools/portal">Synapse Portal IDE</a> </p>
<p> </p>
<p> </p>
<p><span class="wysiwyg-font-size-x-large">Software Re-Installation / Creating your own product</span></p>
<p><strong><span class="wysiwyg-font-size-large">E10 Gateway</span></strong></p>
<p>The E10 in this kit should be pre-programmed with the Exosite gateway reference code.  If you need to re-install the software or you'd like to create your own kit, here are the instructions for updating your E10.</p>
<p><span style="text-decoration: underline;"><strong>Software Installation</strong></span></p>
<p><span style="text-decoration: underline;">Required Software</span></p>
<ul>
<li><a href="https://github.com/exosite-labs/pyonep">Pyonep - Exosite Python Library</a></li>
<li>SNAP Connect - Synapse Python Library (Version 3.1.0 or higher)</li>
<li>Gateway Core - Exosite Gateway Framework </li>
<li>Application - The actual evaluation application that runs on the gateway.  This is automatically downloaded and ran by the Gateway Core framework.</li>
</ul>
<p> All of these items are found in the attached zip file with an installer script.  Please submit a support ticket to get this installer at this time.  This installer can be run from a USB Flash drive connected to the E10 or over a network connection:</p>
<p><span style="text-decoration: underline;">Instructions for installation with a USB Flash Drive:</span></p>
<ol>
<li>Unzip the contents of exosite_snape10_eval_kit_installer.zip onto USB Flash Drive. There should be a directory folder called 'installer' on your USB Flash Drive now.</li>
<li>Plug the USB Flash Drive into the E10</li>
<li>Mount the USB Flash Drive with the following commands using the E10 command prompt:</li>
<ol>
<li><em><strong>mdev -s</strong></em></li>
<li><em><strong>mount /dev/sda1 /mnt</strong></em></li>
<li><em>After executing the correct command, you should be able to find your USB FLASH drive files under the /mnt directory.</em></li>
</ol>
<li>Go to the installer directory with the following command: <strong><em>cd /mnt/installer</em></strong></li>
<li>Run the command: <em><strong>sh install.sh</strong></em></li>
<li>Reboot the device by powering it off or calling the <em><strong>reboot</strong></em> command.</li>
</ol>
<p>This should install all the required components on the Gateway.  When rebooted, The Gateway Core application will attempt to provision and download the application code.   This installer will blow away any existing the CIK file for the gateway and thus<strong> the Gateway will need to be re-enabled on your Exosite portal</strong>.</p>
<p> </p>
<p><strong><span class="wysiwyg-font-size-large">RF Engines / Protoboards</span></strong></p>
<p><span class="wysiwyg-font-size-medium wysiwyg-font-size-x-large wysiwyg-font-size-large">The RF Engines / Protoboards in this kit should be pre-programmed with reference code that will work with the E10 gateway code including trying to pair to a E10 gateway, provisioning, and writing data.  If you need to re-install the software or you'd like to create your own kit, here are the instructions for updating your node.</span></p>
<p><span class="wysiwyg-font-size-medium"><strong style="font-size: 13px;">Software Installation</strong></span></p>
<p><span style="text-decoration: underline;">Required Software</span></p>
<ul>
<li>SNAP Module Python Application (Attached)</li>
<li>Synapse Portal - IDE to program your SNAP RF Engines</li>
<ul>
<li>Recommend using a SNAP USB Stick with this although it is possible to use your E10 connected to your computer or to connect the proto-board directly to your computer via it's serial port.</li>
</ul>
</ul>
<p> The  SNAPpy python application should be programmed on your node using Synapse Portal IDE tool on your computer.  Please submit a support ticket to get the node SNAPpy script.  </p>
<p> </p>
<p> </p>
<p><span class="wysiwyg-font-size-x-large">Troubleshooting</span></p>
<p><strong>Finding the E10 Gateway MAC address</strong></p>
<p style="padding-left: 30px;">The E10's MAC address is located on the bottom and can sometimes be worn away.  You can use the USB connection from the E10 to log into a serial prompt.  At the serial prompt, type 'ifconfig' and look for the MAC address for 'eth0' to be printed out</p>
<p style="padding-left: 30px;"><code># ifconfig eth0<br />eth0 Link encap:Ethernet HWaddr 00:1C:2C:XX:XX:XX<br /> inet addr:192.168.10.33 Bcast:192.168.10.255 Mask:255.255.255.0</code></p>
<p><strong>Can not add a device with specific MAC Address or SNAP Address to your portal</strong></p>
<p style="padding-left: 30px;">If you attempt to add an E10 or a RF Engine node to your portal but receive an error message like the following, there are a few steps to resolve this.</p>
<p style="padding-left: 30px;"><span class="wysiwyg-color-red90"><em><span class="wysiwyg-color-red">You have attempted to add a MAC Address that is not approved for this device. This may be by error. Please verify the exact MAC Address of your device and if you believe it is correct, use the Feedback system to contact us</span></em></span></p>
<p style="padding-left: 30px;">The first is to verify you have the correct unique MAC Address or SNAP Address.  This is important to double check the sticker and possibly even the Debug USB port output.  </p>
<p style="padding-left: 30px;">Next, contact the support team using the 'HELP' tab on the web portal or create a ticket <a href="/hc/en-us/requests/new">through this support site</a>.  Let us know the unique hardware address, the device type (E10 or RF Engine node), and your email and other contact information.  If a previous user has registered the device but not deleted it, the support team will take action to resolve this situation as fast as possible.</p>
<p> </p>
<p> </p>
