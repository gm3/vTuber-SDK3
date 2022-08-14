# vTuber Studio SDK3

###### tags: `vtuber` `virtual production`


## Summary
This is a project for doing virtual productions in VRChat SDK3 (Udon using uSharp). 
It features a system with 9 cameras, and 12 overlay slides. This studio features realtime lighting and a video screen that can play videos. Use these tools to capture multi-camera realtime footage from within vrchat.

## Usage
vTuber Studio SDK3 v0.2.0-alpha running on Unity 2019.4.31f1 
https://github.com/gm3/vTuber-SDK3/releases

Extract the project, and open with Unity 2019.4.31f1  and you will have to wait for the Library to rebuild. 
The shader varients need to compile as well and it takes quite a while. 
After you compile the project once, you can go into the Project Settings -> Graphics and save the shader varients to make the project compile faster. 

![](https://i.imgur.com/DHikM0z.jpg)

## Instructions (Keyboard Controls for PC User)
* 1-9 keys will swap between cameras
* Zero Key (0) goes to Overlay mode
* F - Map Cameras To Screen
* L - Hand Held Camera Light
* G - Greenscreen
* H - show hide video player
* M - Mirror Toggle
* T - Studio Lights Toggle
* P - Reflection Probe Toggle
* U - Toggle All Cameras On and Off
* K - Photo Screen Backdrop Toggle
* O - Camera Preview Toggle

Slides (Use Numeric Keypad)
* 0-9, (.), (+) to change slides

![](https://i.imgur.com/Xm91VYz.jpg)


### Camera Controls
When the keyboard controls are pressed (1-9) the camera seleted will be Set to Active, while the others are set to Inactive. This will feed the main camera output(render texture) The camera previews can be seen on the camera preview panel using Render textures as well( at a lower resolution for optimization. ) The camera previews are a duplicate of the main camera with all of the exact same parameters, except they feed a render texture so that you can preview the cameras before switching.




### General Workflow
To make a custom production, we create and customize a set, configure the locations of the cameras, animate the cameras, then during runtime, we use the keys 1-9 to switch between these cameras with a camera operator in real time. 

![](https://i.imgur.com/OJqAOOc.png)


VRChat is our networked IK, motion capture, and avatar production layer. We are capturing the video output with OBS (Open Broadcast Software) from the Unity game engine. 


### Slides / Overlay
We swap out 12 different Slides(show/hide gameObjects) using the numeric keypad. 
You can swap out the pictures of the slides (that are up in the sky in world space) before building the production by changing the textures in the SLIDES folder, by editing the materials. We import jpegs, and add them to the respective materials before we do the production. A possible extention to this would be to use a URLLoader to have dynamic materials and slides. 

![](https://i.imgur.com/CJQKnd7.png)


### Arranging The Cameras
Move the cameras (via the Parent Object) and feel free to animate or extend the cameras to do even more things like add more scripts and functionality as needed. Make sure to put the rigid body, and pickup scripts on the parent object to maintain the camera heirchy. Arrange the cameras around your set by translating the cameras manually, and checking the camera preview object to see how it looks in frame.

### Pro-Tip: 
Because of the way the camera previews work, you should only move the Master Root of each camera. You can add an additional Parent object to the cameras if you like, and animate those for animated camera tracks. 

![](https://i.imgur.com/8D22FFv.png)

### Camera Culling / Hiding Objects From Cameras
If you would like to hide / show things in the camera output, you would setup layers and use camera culling with a "SeenByCamera" layer. Also if you use greenscreen consider culling it from the refelction probe. 

![](https://i.imgur.com/vBScaE1.png)

### Reflection Probes
You can push P to disable / enable realtime reflections vr baked ones. (Realtime Looks Better but has a performance cost)

![](https://i.imgur.com/iQMTAB6.png)

## Dependencies
- Unity **Unity 2019.4.31f1.**  https://docs.vrchat.com/docs/current-unity-version
- **VRChat SDK3** https://vrchat.com/home/download
- Udon Sharp by Merlin https://github.com/MerlinVR/UdonSharp
- "uSharp Video Player" by Merlin https://github.com/MerlinVR/USharpVideo
- Wolfe Video Player (Udon) https://vrchat.nishawolfe.com/prefabs/videoplayer
- LTCGI by PI https://github.com/PiMaker/ltcgi
- AvatarLight by PI https://github.com/PiMaker/VRChatUnityThings
- lox9973's VideoRT https://drive.google.com/file/d/1XQBybXg2D87AueLI87UuujA3jDN4fU33/view https://github.com/PiMaker/VRChatUnityThings
- JetDogs Prefabs (Udon) https://github.com/jetdog8808/Jetdogs-Prefabs-Udon


## Web Resources:
* http://Unity3d.com/
* http://vrchat.com/

## Community

Please check out some our productions on [Youtube](https://www.youtube.com/results?search_query=godfrey+meyer&page=&utm_source=opensearch) "Godfrey Meyer" or [#boomboxhead](https://www.youtube.com/results?search_query=%23boomboxhead) to find videos. If you have any questions please feel free to reach out us in the M3 Discord https://discord.gg/JvCd2QWkeH
