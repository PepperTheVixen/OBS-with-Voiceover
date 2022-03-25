# OBS-with-Voiceover
This is a guide to help Voiceover users successfully navigate and use OBS for Mac OS.


# Getting started
So, you want to use OBS. You want to stream to Twitch or YouTube or what have you. You downloaded the software. Maybe you even got it through Home-brew. You made sure Rosetta was installed, ran the app, and promptly ran screaming as you were slammed by a wall of laughably inaccessible controls. Don’t be too discouraged. Where there’s a will, there’s a way, and I’m here to show you how to brave the… quirks of this QT-powered program.
## Before beginning
There are two things we must take care of before proceeding. First off, we’re going to need some software. Second, you must be okay with the fact that you will likely need sighted assistance at some point. If you’re still willing, let us proceed.


 First, I strongly recommend you install [VOCR](https://github.com/chigkim/vocr) on your Mac. This handy software gives you optical character recognition right on your Mac! Follow the instructions and read the readme. It will show you how to use it, and do make sure the app is running as it won’t run on startup by default.
## Setting up OBS with the basics.
When you first run OBS, you may be prompted to install Rosetta. You can build a version that works natively yourself, but that’s beyond the scope of this guide. Once it’s up and running, you should be dumped into the auto configuration wizard. If it doesn’t, you can find it under tools in the menu bar with VO+m.


This is where the weirdness starts. You won’t be able to proceed very far before you encounter the first obstacle: a combo box. Instead of using the Voiceover cursor to select, you’ll need to move the mouse cursor to the combo box with VO+cmd+fn+f5. Then Click the mouse with VO+shift+space. After a few seconds, Voiceover will announce “OBS has new window”. Instead of holding VO and pressing fn+f2 twice, hold VO and press fn+f1 twice and navigate to the OBS application and hit the right arrow to find the OBS windows. For whatever reason, Voiceover will announce that OBS is not responding if you try to use the window chooser instead of the application chooser. Once you get to the OBS windows, select the one that’s named the same as whatever option is currently selected in the combo box. You can then use VO and the arrows to move up and down the list of options. When you find the option you want, move the mouse there and click the mouse using the previous commands for said actions. If you’re not already, get comfortable doing this because OBS requires a lot of it.
## Logging into Twitch
I use Twitch, so I can only speak for this service in particular. I recommend logging in. It gives OBS better integration, and it also avoids the usage of a stream key. OBS obfuscates it by default, so the risk of showing it live is low but not zero. Giving out your stream key, even unintentionally, can spell certain death for your channel as it will allow anyone to stream as if they were you. Guard it with your life. Reset it on Twitch if you have any suspicions that it may have been leaked. This is the most painful part of the setup process. If VOCR isn’t already running, make sure to open it up. If you don’t know how to use it, go back to the readme file on Github. If You don’t want to or can’t use VOCR, the alternative is to get your stream key from the website and paste it into OBS when prompted. Now onto logging in with Twitch. When you press the button to do so, you will be taken to a web view that is completely and entirely inaccessible to Voiceover. Don’t worry, just use VOCR and move the Voiceover cursor to the username text. Move the mouse cursor there and Click and type your username. You can exit OCR and rescan to confirm that it was typed into the appropriate area. It should appear immediately below the username text. Press tab to move to the password field, type it in, and then press enter. Depending on your security settings, you may be prompted for a security code. Use the same techniques you just used to enter that in and press enter or use VOCR to navigate to the “okay” text and click it. You should now be logged into Twitch. You’ll be presented with two inaccessible windows. You can VOCR these, but you can’t interact much with them even with that, so use the application chooser (the window chooser should work here as well) to move back to the main OBS window or the configuration wizard, depending on when you do this. I’ll show you how to get rid of these permanently later. Yes, they give you access to chat and stream info, but using VOCR to read chat in real-time is a bad proposition, and changing your stream info will be more accessible through the website or the iOS app.


Did you make it? Congrats. Next up, run the bandwidth tester, accept the settings if you’re happy with them, and you should be good.
## Interface description
OBS doesn’t have nice logical groups. At the top of the Window, you’ll first encounter the version number. After that will be info on the selected source. Yours will likely be text that says “no source selected” followed by “text” followed by a properties button and a filter button. After this will be a series of more text. Each text item is a scene. They don’t show up as buttons, but they can be clicked by moving the mouse cursor there and clicking it to activate them. If you’re streaming, you’ll probably want to have 4 or 5 scenes for various functions like an intro, hold screen, blank screen, outro, and so on. We’ll get to that later. After this will be another string of text items which are the names of your sources. You probably won’t have any at this point. There is no logical distinction between these two groups, so you’re going to have to be meticulous about how you name your scenes and sources. If all you want OBS for is to record your webcam, then this won’t be as confusing since you’ll only have one scene followed by one or more sources.


After this, you’ll come across the mixer section. There should be a device called “mic/aux”. This is a global device that will show up in all scenes and pulls audio from your default input device. If you have more than one audio source, you will come across more than one set of audio controls. There will also be a properties button for each. A word of warning. You will come across a checkbox to mute your audio. The Voiceover cursor will find this checkbox. It will check this checkbox. You will think the audio is muted. It is not muted. Your mic is still hot. Worse yet, your sighted friend will see what appears to be visual feedback that the mic is muted. This is a big, fat, stinky, brown steaming lie to lull you into a false sense of security before it moves in for the kill. Move the mouse cursor there and click it. This will also check the checkbox, but it will actually mute the audio. Like I said earlier, get used to moving the mouse around with Voiceover commands. The sprinklings of madness are present throughout all of OBS. This issue is currently being tracked on Github, but it may simply be a quirk of QT which is what was used to build OBS. Until told otherwise, assume that all checkboxes in all of OBS are mustache-twirling villains waiting for the next unsuspecting blind person to check them with the Voiceover cursor instead of the mouse cursor.


After the mixer, you’ll come across transition properties. The combo box should be set to “fade” by default. I have yet to find a way to change this, so we seem to be stuck with the crossfade transition for now. After that is a “transition properties” button which seems to do nothing at all. After that, you’ll find the button. The one. “Start Streaming”. Actually, it’s a checkbox. Remember what I said about checkboxes. After that is some curious “duration” text with a stepper set to 300. This is the duration of your transition in milliseconds. Set it to 1000 to make your fades last 1 second. You should be able to delete the text and type in a number manually. Past that are buttons to start recording and start the virtual camera. Again, remember what I said about checkboxes. After that is another checkbox button thing for studio mode, followed by the settings button. The settings button will work with a simple Voiceover press, thankfully.


Lastly, we have a bunch of mysterious text items: add, remove, move up, move down. These are actually buttons you press with the mouse cursor in order to manipulate scenes. Moving up and down refers to moving the order in which they appear at the top of the window. After that, you will find more text items labeled as follows: add, remove, properties, move up, move down. These do much the same for your sources instead of scenes, but you must press these with the Voiceover cursor instead. Beyond that little sprinkling of madness is the exit button. It is merciful and works with a Voiceover press. After that is some text which simply reads “text”. It exists for some reason.
## Adding a Source
This is the next pain point in OBS, but if you made it through the configuration wizard (and especially if you made it through the Twitch login), then you already have the knowledge to do what comes next. Move all the way to the bottom of the window and find the “add” text that’s furthest down. Press it with the Voiceover cursor. After a few seconds, Voiceover will announce “OBS has new window”. HOLD VO and press fn+f1 twice. Find OBS and hit right to view the windows. There should be one named “semicolon untitled” or simply “untitled”. It can change for some reason. Voiceover should announce “menu” once selected. Move the mouse cursor here. Now move the Voiceover cursor to the mouse cursor with VO+shift+fn+f5. You should now be in a menu you can navigate with VO and the arrow keys. Find the type of source you want to add. If you want to record your screen, select display capture. If you want to grab a specific window, use window capture. You can also add browser sources. For example, if you use a PNGtuber avatar, then you may use a browser source along with Discord for voice detection. Select the one you want with the Voiceover cursor. You’ll be dumped into a new window where you can name the new source. It will automatically be added to the currently selected scene. Press okay with the Voiceover cursor at the bottom of the window. You’ll be moved to another window where you can set up the specifics. If adding images or media sources, it’s best if their resolution matches your stream resolution, otherwise it may not be centered or sized properly. This can be fixed quite easily if they don’t match up though. This is where there is no good way around it. If you want to position items on the screen (like an avatar or webcam view in the corner) then you’re going to need the assistance of a sighted person. You can resize the windows with the steppers, but positioning is beyond our ability at the time of writing. You may also come across combo boxes. You’ll have to use the same rigmarole as before: move the mouse cursor there, click, go into the new window with window chooser, find the option you want, move the mouse cursor there, click. Good to go. Press okay when you’re all done and your source will be added to the scene.


When it comes to media sources like images and audio, I recommend to create an asset library with standardized names. I have a folder in my home directory. This makes it much easier to quickly swap out assets between streams by simply dropping in files and giving them the correct name.
## Working in the main OBS interface
So, you have a source. Maybe you have more than one source. Hopefully you got through it all. Let’s talk about the main window some more! I already mentioned some stuff in the interface description. Some items can be pressed with the Voiceover cursor. Some items can be pressed with the mouse cursor. Rule of thumb: if VO+space doesn’t work, use the mouse cursor and vice versa. If you come across a checkbox, assume it wants to murder you in your sleep and use the mouse cursor to check and uncheck it.
