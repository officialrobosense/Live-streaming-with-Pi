# Live-streaming-with-Pi
Live Streaming with 


Step 1: Gather the Components
 Picture of Gather the Components
 Picture of Gather the Components
 Picture of Gather the Components 2 More Images
 In this project, you will need the following:

Raspberry Pi 3 Model B (Any version will work, but in PI 3 we have the provision for WiFi that can make this server wireless)
USB Webcam (I will use my old Logitech Webcam. Use a better camera for better results.)
5V 2A Power Source (I will use my Honor 13000mah Power Bank )
Lan Cable ( RJ - 45 Cable )
Minimum 8 GB Class 10 SD Card ( I will use Sandisk 32GB class 10 SD Card )
If you haven't install the Raspbian OS on the SD card, then you will need a memory card reader and checkout our tutorial on how to install the OS in Raspberry Pi.

Add TipAsk QuestionCommentDownload
Step 2: Set Up Your Raspberry Pi
 Picture of Set Up Your Raspberry Pi
 Picture of Set Up Your Raspberry Pi
 Picture of Set Up Your Raspberry Pi
 We assume you have the SD Card with the raspbian OS installed.

Then insert the SD Card in the Pi.

Connect the USB camera to any one of the four available USB port.

Connect the ethernet cable aka LAN cable to your Pi and connect the other end to your router.

Then Power Up the Raspberry Pi.

The next step is only for Raspberry Pi 3 users. Others. go to step 4.

Add TipAsk QuestionCommentDownload
Step 3: Connect Your Pi to Internet Through WiFi (only for Raspberry Pi 3 Users)
Open the desktop of Raspbian and connect to WiFi by putting the correct password.

When the raspbian is connected to the network by WiFi, then shut down the system.

Now detach the LAN cable and restart. Then you must be connected to the Internet via WiFi only.

This will help to move your webcam and the pi anywhere without the RJ-45 cable.

Add TipAsk QuestionCommentDownload
Step 4: Know Your Raspberry Pi IP Address
 Picture of Know Your Raspberry Pi IP Address
 Picture of Know Your Raspberry Pi IP Address
 Do the following steps to view Pi IP address.

Open your browser on laptop or mobile. ( laptop or mobile has to be in the same network as the pi )
Go to your Router settings by typing in the default IP address of your router. ( written somewhere on your router. )
Find the list of connected devices.
Find the corresponding IP address of the device named raspberry.
In our case, it is 192.168.0.107

Add TipAsk QuestionCommentDownload
Step 5: Connect to Your Pi by SSH Connection ( PUTTY )
 Picture of Connect to Your Pi by SSH Connection ( PUTTY )
 Picture of Connect to Your Pi by SSH Connection ( PUTTY )
 Open up Putty and type in the IP address of your Pi and connect.

'pi' & 'raspberry' is the default 'login as' and 'password' in Raspbian.

It is always a good practice to Update and Upgrade the system as soon as you log in.

To do it, type in the command 'sudo apt-get update' and 'sudo apt-get upgrade' one at a time.

Add TipAsk QuestionCommentDownload
Step 6: Install the Software and Do the Necessary Settings
 Picture of Install the Software and Do the Necessary Settings
 Picture of Install the Software and Do the Necessary Settings
 Picture of Install the Software and Do the Necessary Settings
 Picture of Install the Software and Do the Necessary Settings 6 More Images
 Type in the command 'sudo apt-get install motion ' to start the installation.

Now to make sure that the camera is correctly detected.

Type in the command 'lsusb' and enter. You should see the name of your camera. If it is NOT there, then there is some problem in your camera or the camera is not supported in 'motion'.

After the installation is complete, type in the command ' sudo nano /etc/motion/motion.conf ' and press enter.

Then you have to change some settings in the .conf file. It might be difficult sometimes to find the settings but use 'ctrl + w' to find it. So follow the steps:

Make sure 'daemon' is ON.
Set 'framerate' anywhere in between 1000 to 1500.
Keep 'Stream_port' to 8081.
'Stream_quality' should be 100.
Change 'Stream_localhost' to OFF.
Change 'webcontrol_localhost' to OFF.
Set 'quality' to 100.
Set 'width' & 'height' to 640 & 480.
Set 'post_capture' to 5.
Press ctrl + x to exit. Type y to save and enter to conform.
Again type in the command 'sudo nano /etc/default/motion ' and press enter.

Set ' start_motion_daemon ' to yes. Save and exit.

Add TipAsk QuestionCommentDownload
Step 7: Start the Server
 Picture of Start the Server
First of all your have to restart the motion software. To do it type in the command 'sudo service motion restart' and press enter.

Again type in the command 'sudo motion' and press enter.

Add TipAsk QuestionCommentDownload
Step 8: It's DONE!!
 Picture of It's DONE!
 Picture of It's DONE!
 Picture of It's DONE!
 Picture of It's DONE!
 Now open up your browser. Type in the IP address of your raspberry Pi and the port number in this way:

192.168.0.107:8081 (First there is the IP address, then a ':', then the port number). Press Enter.

Now you can see the Live feed coming from your webcam directly on your laptop or mobile or both at the same time.
