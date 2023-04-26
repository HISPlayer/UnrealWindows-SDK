# Setup Guide
Through this guide, you will be introduced to the basic steps for setting up the playback.

## Import Package
First, extract the SDK from the .zip file, copy the **HISPlayer** folder and paste into the **Plugins/** directory in your project’s root (If that directory doesn’t exist, create one).

<p align="center">
<img src="./images/root-dir.png">
</p>

Then, go into the HISPlayer directory and check that the engine version in your **HISPlayer.uplugin** file is the same as your project’s Unreal version.

<p align="center">
<img src="./images/uplugin-file.png">
</p>

Open your project and go into Edit > Plugins, look for the HISPlayer plugin and if it’s disabled, enable it and restart the project.

<p align="center">
<img src="./images/hisplayer-plugin.png">
</p>

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

## Configure HISPlayer properties
Set the player’s parameters as desired in your **HISPlayer_Blueprint** actor.

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
