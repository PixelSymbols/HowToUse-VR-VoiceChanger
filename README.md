# HowToUse-VR-VoiceChanger
This guide is dedicated for pico 4, but you can make it for any other headset

So this is how i did it. My plan was to use voicechanger in vrchat, and also have ability to stream with obs and record own voice. Also i wanted to have ability to mute myself anytime i want using controller button.
I did this using 3 apps. If you want todo the same thing, follow this tutorial:

1) Install [voicemod](https://www.voicemod.net/) (you can use any other voicechanger, but this is best for me).
2) Install [OpenVR2Key](https://github.com/BOLL7708/OpenVR2Key/). You would need it to bind controller buttons so you could toggle mute and unmute.
3) Install [Voicemeeter Banana](https://vb-audio.com/Voicemeeter/banana.htm). You should install the banana version , because it has ability to set hotkeys.
If you use voicemod or any other voicechanger software that able you to set hotkeys too, and you dont care about setting up mic quality settings, you can ignore this step. I use it not only to set hotkeys, but also to remove echo and make mic sound better.

i will call Voicemeeter banana as VB
STEPS:
1. open VB and set your mic into any hardware input channel. I set mine to 1st. Choose your headset mic:<br>
![](https://user-images.githubusercontent.com/81364140/227792112-4f5c8df0-c984-4b39-ba54-1f04eaedbc70.png)

	you can also tweak this panel so your mic would sound better:<br>
	  ![](https://user-images.githubusercontent.com/81364140/227792099-640b7b68-8e0b-46d2-b775-f85a5a1a4b9c.png)
2. goto menu <br>![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595588745646110/image.png)
run macrobuttons on voicemeeter start (if you would want to change your hotkeys later, you should disable and enable this button so hotkey panel will appear)<br>
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595588942762135/image.png)
click on any square with right mouse button. I set 2 because i use also my desktop mic sometimes.
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595590603706489/image.png)
copy settings marked with red. Everything that is in purple set as you would want. Set any Button name, set hotkey on your keyboard that you want to use and most importantly in the `Request for button` sections set strip number to the `hardware input` number you set your mic to (***You should set with x-1 index: If you set your mic to hardware input 1, you should put 0, if input 2 you should set 1 and etc.***)
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089597767116148736/image.png)
press ok
you should not close this panel, cuz if you do, hotkeys wont work. **it must stay open**
3. If you want to use voicechanger too, then:
	 press here to choose output. You should place here**any** output device except your main one. Otherwise voice changer such as voicemod wont work, because VB would use the same output as voicemod. 

	Otherwise, if you want to use just voicemeeter, choose your main output device.
	Again, you can choose any channel, i chosen A1.
<br>

![](https://user-images.githubusercontent.com/81364140/227793599-4b5c4482-6a76-45fb-a303-a3d253df57a4.png)

5. go again to menu and press save to save your preset as file
save settings <br>![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595589433495682/image.png)
and load settings on startup. Choose your saved file<br>![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595589144100996/image.png)
so when you will start voicemeeter, it will automaticly load everything u did. You can also test your hotkey by pressing button and watching on state of **"mute"**<br>
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089595589752279051/image.png)
if it works, you did everything correctly, otherwise please reread.

6. Now run your voicechanger and put input as **VB** and output to your main output device.<br>
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089601156172484690/image.png)
7. Run OpenVR2Key.
![](https://cdn.discordapp.com/attachments/1027900116339793953/1089601381637300275/image.png)
Run your headset/steamvr, so basically connect your pico 4 or quest 2 to pc and wait in main lobby. Goto your pc and press the button u want to bind to mute your mic, and press it. You should see its id in ***Current app ID***. Remember it and scroll down to mapping, find it there, and bind the key u binded in **VB**. After u done it, if it marked red, click **esc**, so it should be gray again (look at screenshot. I bind **L9 key**, its **X key** on left controller of **Pico 4**). It should work.

Thats all. If you have troubles, reread guide again and also remember to test everything after each step. I dont think it would be hard, you can do it =3


BONUS:
here i wrote bat file to start everything automaticly:<br>
```bat
cd "C:\Program Files (x86)\VB\Voicemeeter"
start "" "voicemeeterpro.exe"
timeout /t 7
cd "C:\Program Files\Voicemod Desktop"
start "" "VoicemodDesktop.exe"
timeout /t 4
cd "C:\MyData\Documents\OpenVR2Key (Hotkeys for PICO)"
start "" "OpenVR2Key.exe"
timeout /t 2
cd "C:\Program Files\Streaming Assistant"
start "" "Streaming Assistant.exe"
```
