# Head Tracking 3D Parallax Effect, using Unreal Engine and a Kinect Camera
### Demo Video:
https://youtu.be/Gnx1KWlHqXc

<p align="center">
<img src="Images/DemoImage.PNG" alt="Crossover Points" width = "85%" height="50%"></img>
</p>

---
## 

This repository contains the UE5 project used to set up the 3D display effect, including the assets and blueprints.

## Set Up Instructions

Create a new Unreal Engine project, the version should be 5.0 or higher, this project has only been tested with version 5.0. and 5.2.

Install the ’Azure Kinect SDK’ and the ’Azure Kinect Body Tracking SDK’ from Microsoft’s website.

### Create the following two System Environment variables:
* AZUREKINECT_SDK that points to the Azure Kinect Body Tracking SDK root path (`C:\Program Files\Azure Kinect SDK v1.4.1`)

* AZUREKINECT_BODY_SDK that points to the Azure Kinect Body Tracking SDK root path (`C:\Program Files\Azure Kinect Body Tracking SDK`)

### Add the following three paths to the PATH system environment variable

* `C:\Program Files\Kinect Body Tracking SDK\sdk\windows-desktop\amd64\release\bin`

*  `C:\Program Files\Azure Kinect SDK v1.4.1\sdk\windows-desktop\amd64\release\bin`

* `C:\Program Files\Azure Kinect SDK v1.4.
1\sdk\netstandard2.0\release`

Create a Plugins folder inside your unreal project folder (Where the .uproject is located)

Clone this repo into the plugins folder.

Test the Azure Kinect Device using the preview applications in the tools folder of each
SDK. 

Ensure the following plugins are installed: LiveLinkXR, LiveLink Over nDisplay,
nDisplay, Switchboard. 

Restart the Engine once these plugins have been enabled.

## nDisplay Setup with Unreal Engine

Place the nDisplay Actor in the scene in the
location that the virtual screen should appear. 
If your screen is not a 27 inch monitor, replace the Static Mesh Component of the screen with the custom model of your display. In Cluster drop down menu, select the Primary Node and set the size to the resolution of the display being used. Also Update the Region Size of the the new nDisplay Config. Add a New Cluster Node and set the resolution to match the resolution of the display being used. In this implementation the resolution was 1920x1080 for the monitor and 3840x1080 for the LED wall. nDisplay is capable of using multiple connected computers to render the scene. If just one computer is being used, the IP address should be set to 127.0.0.1. Ensure the Projection Policy Type is set to ”Mesh” and the Mesh option is set to the imported screen mesh. Launching the application. 

### Launching The Application from Switchboard

The application needs to be launched from within Switchboard which was installed with the nDisplay plugin. Switchboard is the dashboard used to manage nDisplay with several computers and several displays. Run Switchboard and Switchboard Listener on your desktop by searching for them in the start menu. On the Switchboard Change the device setting to nDisplay and browse for the reference to the nDisplay asset (.uasset) in the folder where your Unreal Engine project is located. Once this is located, the specific level needs to be selected from a drop-down menu. Now Switchboard can be connected using to Unreal Engine using the connect icon, and the application can finally be built and ran by clicking the build icon.

<br>
<br>
<p align="center">
<img src="Images/nDisplay Example.png" alt="Crossover Points" width = "60%" height="50%"></img>
</p>