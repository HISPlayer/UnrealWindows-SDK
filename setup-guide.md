# Setup Guide
Through this guide, you will be introduced to the basic steps for setting up the playback.

## Import Package
First, extract the SDK from the .zip file, copy the **HISPlayer** folder and paste into the **Plugins/** directory in your project’s root (If that directory doesn’t exist, create one).

<p align="center">
<img src="./images/root-dir.png">
</p>

Then, go into the HISPlayer directory and check that the engine version in your **HISPlayer.uplugin** file is the same as your project’s Unreal version. 
The "Engine Version" field will only take into account the major and middle version number (For example, if you are using UE 5.3.2, just add 5.3.0 to that field).

<p align="center">
<img src="./images/uplugin-file.png">
</p>

Open your project and go into Edit > Plugins, look for the HISPlayer plugin and if it’s disabled, enable it and restart the project.

<p align="center">
<img src="./images/hisplayer-plugin.png">
</p>

## Set Default Build Settings Version
It is preferable to use the HISPlayer SDK in a C++ project, rather than in an only blueprint one. To create a C++ project from an only blueprint project, go to **Tools > New C++ Class** and follow the indications to create a new one. Any kind of C++ parent class will work.

<p align="center">
<img src="./images/CreateScript.png">
</p>

For UE versions 5.0, 5.1, 5.2 and 5.3 it is necessary to set the DefaultBuildSettings to BuildSettingsVersion.V2. In order to do so, please add the line `DefaultBuildSettings = BuildSettingsVersion.V2;` in the `"YourProjectName".Target.cs` and `"YourProjectName"Editor.Target.cs` scripts, located in the `Source` directory: 

<p align="center">
<img src="./images/TargetSettings.png">
</p>

The HISPlayerSample and HISPlayerVRSample are C++ projects which already include this lines of code so, in case you are using them, you can skip to the next section.

## Import HISPlayer_Blueprint
To use HISPlayer’s functionalities in your Level, you need to add the **HISPlayer_Blueprint**. The is located inside **Content Browser > HISPlayer Content > Blueprint**.

<p align="center">
<img src="./images/browser-structure.png">
</p>

If you can’t find the **HISPlayer Content directory** in the Content Browser, check “Show Plugin Content” in “View Options”.

<p align="center">
<img src="./images/show-content.png">
</p>

Add the **HISPlayer_Blueprint**.

<p align="center">
<img src="./images/insert-blueprint.png">
</p>

To render the content, you need to set an actor with **HISPlayer_Material** as Material.

<p align="center">
<img src="./images/add-actor.png">
</p>

## Configure HISPlayer multistream properties
Set the player’s parameters as desired in your **HISPlayer_Blueprint** actor for single stream and multistream.
It is possible to add more than one stream using one instance of the **HISPlayer_Blueprint**, by adding more elements to the Stream URL and Target Actors arrays.

<p align="center">
<img src="./images/playback-props.png">
</p>

You can modify the behavior of the **HISPlayer_Blueprint** as desired or use a custom blueprint, as long as it follows the original structure.

<p align="center">
<img src="./images/graphic.png">
</p>

Use the **HISPlayer API** to add your own implementation.

<p align="center">
<img src="./images/sample.png">
</p>

## License Key
Input the license key that is associated with the SDK. If the license key is not valid, the player won’t work and will throw an error message. To find this field, go to the Level Outliner and look for the HISPlayer_Blueprint actor. Then, on the Details window, look for the HISPlayer section.

<p align="center">
<img src="./images/licensekey.png">
</p>

## Disable Anti-Aliasing
If you are experiencing a ghosting effect on the stream, then you will need to disable the anti-aliasing effect on your project. 
To do that on Unreal 5, go to **Edit > Project Settings > Engine > Rendering > Default Settings > Anti-Aliasing Method** and set it to **None**.

<p align="center">
<img src="./images/AntiAliasing.png">
</p>

## Default RHIs
Make sure that the **Default RHIs** option is settled to **DirectX11** or **DirectX12**. Otherwise, go to **Edit > Project Settings > Platforms > Windows > Targeted RHIs**.

<p align="center">
<img src="./images/DefaultRHI.png">
</p>

## Packaging the project
In order to package the project, you need to make sure that **Your_Project.uproject** file has been correctly updated on the **“Plugins”** field:

<p align="center">
<img src="./images/PluginUproject.png">
</p>

You can update this file manually, or by clicking on the Update button when this message appears when opening the project with the plugin installed.

<p align="center">
<img src="./images/Update.png">
</p>

Depending on the Unreal version, it is also possible that you need to generate a visual studio project, if you are working on a Blueprint project.

Finally, after packaging the project, you will need to create a new folder called Plugins inside **Your_BuildRootDirectory > Your_ProjectName** folder, and paste there the HISPlayer folder plugin (similar to the Import Package step)

<p align="center">
<img src="./images/Build.png">
</p>

## Setting up PCM Audio Data
It is possible to retrieve the PCM data of a stream at runtime. To start the retrieval process, call the **HISPlayer Start PCM Data Process** function. To stop the process, call the **HISPlayer Stop PCM Data Process**. It is important to stop the process before releasing the player. 

<p align="center">
<img src="./images/PCM.png">
</p>

Every time new PCM data is being received, it is possible to get it in a **TArray\<float>** format, along with the stream's timestamp, by using the **On PCM Data Received Event**.

<p align="center">
<img src="./images/PCMevent.png">
</p>

Getting the PCM data of a stream is computationally expensive, so its recomended to use it only on a single stream, event though this functionality is compatible with multistream. 

## Updating the SDK

To update a HISPlayer SDK of a previous version, please follow these steps:
* Go to your Root project folder > Plugins and delete the HISPlayer folder.
* Paste your new HISPlayer SDK folder inside the Plugins folder.
* Go again to your Root project folder and delete the Binaries and Intermediate folders.
* Execute Your_Project.uproject file.

Make sure that your project is closed while doing this process.
