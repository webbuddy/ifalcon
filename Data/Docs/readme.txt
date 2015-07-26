This application is designed for the ipad2 and serves to emulate a 2D cockpit to better enable touchscreen clicking on the most common used panels in the F16 cockpit.  
Images used are the included 2D images in the Falcon installation which have been mapped with hotspots on the various panels, buttons and switches.
Overlay images are used to enlarge certaina reas of the 2D cockpit to make some panels larger and therefore easier to access and use.  To close an overlay touch anywhere off the overlay or touch the close icon, usually at the top right hand corner.
Touching any of the button/switch hotspots will send the appropriate keystroke from the ipad to your desktop box where falcon is installed.  Hotspots have also been created to launch things such as Red Dogs Interactive Map of Korea, as well as his excellent Checklists, which are also included in your Falcon install.

INSTALLATION:
Download the <a href="http://dl.dropbox.com/u/1409877/Awesome%20Force/Touch/iFalcon.zip">iFalcon</a>complete package <a href="http://dl.dropbox.com/u/1409877/Awesome%20Force/Touch/iFalcon.zip">here</a>.


Unzip the iFalcon.zip to a folder of your choosing (no installation required)

Launch the WebServer application (TouchDown Web Server Beta 0.3.1.0)in the iFalcon folder
Make sure the profile page is "index.htm"
and the IP address is the LAN IP of your desktop machine (typically 192.168.X.XX or 10.0.0.X)
In the Setttings menu "Allowed IP" of the WebServer app enter the LAN IP address of your iPad (you can usually find this in your routers attached devices list)
If you are running "TeamViewer" shut it down, it conflicts with WebServer app.
Click "Start Server"

Start your iPad and navigate in Safari to the IP of your desktop Falcon computer
eg 10.0.0.3 or 192.168.0.6
Yes just type the IP in the URL bar and hit enter

If all has gone according to plan your iPad should show a picture of a 2D cockpit with touchable hotspots just waiting for your smudges. See the enclosed READMEcockpit.jpg

HOW TO USE IT:
Touch the Left MFD and a larger MFD opens overlayed atop the cockpit.  Touch any of the 20 OSBs to send those keystroke commands to your desktop computer. Close the MFD by touching the close icon or simply touch anywhere off the MFD to close it  and return to the cockpit.
Try the same thing with the Right MFD, once again all 20 OSBs are mapped appropriately.
From the 2D cockpit, this time touch the ICP, a larger ICP overlay opens and all buttons, are once again touchmapped to send the appropriate keystrokes to your desktop computer. Close the ICP using either method mentioned above and return to the cockpit view.
Some of the more commonly used switches in the 2D pit are also touch mapped and include the following;
Laser Arm (Toggle)
Master Arm (Toggle)
Autopilot switches (both) Up and Down (requires two touches to move from down through middle to up and vice versa)
Gear (Toggle)


TROUBLESHOOTING:
The keystrokes emulated here are based on the BMS.key keystrokes file.  If the keystrokes are incorrect for you then you are using an inferior keystrokes file and its time you "got with the program".
Alternatively you can choose to stick with your keystrokes file which has served you so well this past decade and delve into the .htm files and edit them to emulate the keystrokes you use.
To do this you will need to edit the following files
iFalcon\data\Docs\cockpit.htm (This is the main cockpit view)
iFalcon\data\Docs\LMFD.htm (The Left MFD)
iFalcon\data\Docs\RMFD.htm (The Right MFD)
iFalcon\data\Docs\ICP.htm (The ICP panel)
___________________________________________________________________________
EDITING YOUR BMS.key 
In setting this up I discovered that the BMS.key file had no key assignment for  OSB 19 and 20 on either Left or Right MFD.  
To fix this is a simple copy/paste job, however if you feel that this is beyond you, stop now and go adn watch TV instead.  No responsibility is accepeted for any damage inflicted by yourself on your files, your Falcon installation should you proceed.

To fix this open your BMS.key file in a simple text editor and find the lines

SimCBEOSB_19L 1041 0 0XFFFFFFFF 0 0 0 1 "LMFD OSB-19"
SimCBEOSB_20L 1040 0 0XFFFFFFFF 0 0 0 1 "LMFD OSB-20" 

and replace them with

SimCBEOSB_19L 1041 0 0x49 6 0 0 1 "LMFD OSB-19"
SimCBEOSB_20L 1040 0 0x52 6 0 0 1 "LMFD OSB-20"

Similarly for the Right MFD find the lines

SimCBEOSB_19R 1061 0 0XFFFFFFFF 0 0 0 1 "RMFD OSB-19"
SimCBEOSB_20R 1060 0 0XFFFFFFFF 0 0 0 1 "RMFD OSB-20"

and replace them with

SimCBEOSB_19R 1061 0 0x49 5 0 0 1 "RMFD OSB-19"
SimCBEOSB_20R 1060 0 0x52 5 0 0 1 "RMFD OSB-20"

Your keyfile (which should be based on BMS.key) now has keystrokes for all 40 OSBs.
___________________________________________________________________________


EDITING YOUR HTM FILES
To edit a keystroke in the htm files you need to change the detail inside the () of  the line.
eg, I use an inverted NUMPAD to emulate the keys in the same layout as the pit ICP, but if you use NUMPAD 1 as ICP 1 then you may want to switch these around
So change this...
<area name="A-CAL 9" shape="rect" coords="206,264,252,310" href='function macro("{NUMPAD3}");' target="bottomFrame">
to
<area name="A-CAL 9" shape="rect" coords="206,264,252,310" href='function macro("{NUMPAD9}");' target="bottomFrame">

Make sure you dont mess with any other characters in the code or you will most likely break it.
You will need to do this for ICP 1,2,3,7,8,9

Single keystrokes shoud follow this syntax
<area name="TOGGLE LANDING GEAR" shape="rect" coords="0,552,125,621" href='function macro("g");' target="bottomFrame" title="TOGGLE LANDING GEAR" alt="TOGGLE LANDING GEAR">
Chorded keystrokes should follow this syntax
<area name="WARN RESET" shape="rect" coords="278,369,311,398" href='function macro("+^!w");' target="bottomFrame">
where 	+ is Shift
		^ is Ctrl
		! is Alt
		w is well its just w
___________________________________________________________________________	

WHATS NEXT?

I have been trying to make all the checklists accessible as an overlay as well, but pdfs are proving difficult.  Stay Tuned


