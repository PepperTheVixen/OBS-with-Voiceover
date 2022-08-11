# OBS With VoiceOver

This is a guide to help VoiceOver users successfully navigate and use OBS for macOS.

# Getting started

OBS Studio is open-source software for recording and broadcasting. It's commonly used to stream to websites like Twitch and YouTube. It's very powerful, but its accessibility is not the best, however it is useable. In fact, many blind and visuall-impaired people use it regularly to stream. Operation with a screen reader is very different between Mac OS and Windows. This guide will specifically cover the use of OBS on a Mac.

## Assumptions and caveats

- You are using Mac OS 12 Monterey or later
- You are using OBS Studio 27.2.4 or later. 
- You are familiar with the controls and operation of Mac OS and Voiceover for Mac OS
- You are using VOCR for optical character recognition (see below)
- For keyboards without function-row mappings (such as non-Apple desktop keyboards), it is not necessary to press the fn key

## Useful Resources

- [VoiceOver User Guide for Mac - Apple Support](https://support.apple.com/en-gu/guide/voiceover/welcome/mac)

- [Appendix A. Commands and Gestures](https://www.apple.com/voiceover/info/guide/_1131.html)

## Before beginning

First, you must be okay with the fact that you may need sighted assistance at some point. Some operations, like positioning elements on the canvas cannot be done with Voiceover, and you will need a sighted person to help you. Fortunately, the basics can be done entirely without sight.

Second, this guide will be using [VOCR](https://github.com/chigkim/vocr) for setup. It's extremely useful to have even if you don't use OBS.

Third, this guide uses [OBS Studio](https://obsproject.com/). Download and install the .dmg file for Mac OS. If you have Homebrew, run: `brew install obs`

## Setting up OBS with the basics.

When you first run OBS, you may be prompted to install Rosetta. At this time, Rosetta is required to run OBS. You can build a version that works natively yourself, but that’s beyond the scope of this guide. Once it’s up and running, you should be dumped into the auto configuration wizard. If it doesn’t, you can find it under tools in the menu bar with `VO+M`.

You won’t be able to proceed very far before you encounter the first obstacle: a combo box. When the Voiceover cursor is focused on the combo box, move the mouse cursor to the combo box with `VO+Cmd+fn+F5`. Then Click the mouse with `VO+Shift+Space`. After a few seconds, VoiceOver will announce “OBS has new window”. Hold `VO` and press `fn+F1` twice and navigate to the OBS application and press right arrow to find the OBS windows. For whatever reason, VoiceOver will announce that OBS is not responding if you try to use the window chooser instead of the application chooser. Once you get to the OBS windows, select the one that’s named the same as whatever option is currently selected in the combo box. You can then use VO and the arrows to move up and down the list of options. When you find the option you want, move the mouse there and click the mouse using the previous commands for said actions. This type of selection is common throughout the interface.

## Logging into Twitch

I use Twitch, so I can only speak for this service in particular. I recommend logging in. It gives OBS better integration, and it also avoids the usage of a stream key. OBS obfuscates it by default, so the risk of showing it live is low but not zero. Giving out your stream key, even unintentionally, can spell certain death for your channel as it will allow anyone to stream as if they were you. This is the most painful part of the setup process.
Run VOCR if it is not already running. If You don’t want to or can’t use VOCR, the alternative is to get your stream key from Twitch and paste it into OBS instead of logging in. When you are prompted to log into Twitch in the setup wizard, you will be taken to a web view that is completely inaccessible to VoiceOver. Use VOCR and move the VoiceOver cursor to the username text. Move the mouse cursor there, click, and type your username. You can exit OCR and rescan to confirm that it was typed into the appropriate area. It should appear immediately below the username text. Press tab to move to the password field, type it in, and then press enter. Depending on your security settings, you may be prompted for a security code. Use the same techniques you just used to enter that in and press enter or use VOCR to navigate to the “okay” text and click it. You should now be logged into Twitch. You’ll be presented with two inaccessible windows. You can VOCR these, but you can’t interact much with them even with that, so use the application chooser (the window chooser should work here as well) to move back to the main OBS window or the configuration wizard, depending on when you do this. I’ll show you how to get rid of these permanently later. Yes, they give you access to chat and stream info, but using VOCR to read chat in real-time is a bad proposition, and changing your stream info will be more accessible through the website or the iOS app.
Did you make it? Congrats. Next up, run the bandwidth tester, accept the settings if you’re happy with them, and you should be good.

## Interface description

### Scenes and sources

OBS doesn’t have logical groups like many other Mac OS applications while using Voiceover. At the top of the Window, you’ll first encounter the version number. After that will be info on the selected source. Yours will likely be text that says “no source selected” followed by “text” followed by a properties button and a filter button. After this will be a series of more text. Each text item is a scene. They don’t show up as buttons, but they can be clicked by moving the mouse cursor there and clicking it to activate them. If you’re streaming, you’ll probably want to have 4 or 5 scenes for various functions like an intro, hold screen, blank screen, outro, and so on. We’ll get to that later. After this will be another string of text items which are the names of your sources. You probably won’t have any at this point. There is no logical distinction between these two groups, so you’re going to have to be meticulous about how you name your scenes and sources. If all you want OBS for is to record your webcam, then this won’t be as confusing since you’ll only have one scene followed by one or more sources.

### Audio mixer

Next is the mixer section. There should be a device called “mic/aux”. This is a global device that will show up in all scenes and pulls audio from your default input device. If you have more than one audio source, you will come across more than one set of audio controls. There will also be a properties button for each. A word of warning. You will come across a checkbox to mute your audio. The VoiceOver cursor will find this checkbox. It will check this checkbox. You will think the audio is muted. It is not muted. Your mic is still hot. Your sighted friend will see what appears to be visual feedback that the mic is muted. This is a lie to lull you into a false sense of security. Move the mouse cursor there and click it. This will also check the checkbox, and it will actually mute the audio. This issue is currently being tracked on GitHub ([issue #6200](https://github.com/obsproject/obs-studio/issues/6200)), but it may simply be a quirk of Qt which is what was used to build OBS. Until told otherwise, assume that all checkboxes in all of OBS are waiting for the next unsuspecting blind person to check them with the VoiceOver cursor instead of the mouse cursor.

### Transition and stream controls

After the mixer, you’ll come across transition properties. The combo box should be set to “fade” by default. I have yet to find a way to change this. After that is a “transition properties” button which seems to do nothing at all. After that, you’ll find The most exciting and dangerous button, “Start Streaming”. Actually, it’s a checkbox. Remember the rule about checkboxes. After that is “duration” text with a stepper set to 300. This is the duration of your transition in milliseconds. Set it to 1000 to make your fades last 1 second. You should be able to delete the text and type in a number manually. Past that are buttons to start recording and start the virtual camera. These also work like checkboxes. After that is another checkbox button thing for studio mode, followed by the settings button. The settings button will work with a simple VoiceOver cursor press.

### scene and source controls

Lastly, we have a bunch of mysterious text items: add, remove, move up, move down. These are buttons you press with the mouse cursor in order to manipulate scenes. Moving up and down refers to moving the order in which they appear at the top of the window. After that, you will find more similar text items labeled as follows: add, remove, properties, move up, move down. These do much the same for your sources instead of scenes, but you must press these with the VoiceOver cursor instead. Beyond that little sprinkling of madness is the exit button. It is merciful and works with a VoiceOver press. After that is some text which reads “text”. It exists.

## Adding a Source

This is the next pain point in OBS, but if you made it through the configuration wizard (and especially if you made it through the Twitch login), then you already have the knowledge to do what comes next. Move all the way to the bottom of the window and find the “add” text that’s furthest down. Press it with the VoiceOver cursor. After a few seconds, VoiceOver will announce “OBS has new window”. Use the application chooser to view the windows. There should be one named “semicolon untitled” or simply “untitled”. It can change for some reason. VoiceOver should announce “menu” once selected. Move the mouse cursor here. Now move the VoiceOver cursor to the mouse cursor with VO+shift+fn+f5. You should now be in a menu you can navigate with `VO` and the arrow keys. Find the type of source you want to add. If you want to record your screen, select display capture. If you want to grab a specific window, use window capture. You can also add browser sources. For example, if you use a PNGtuber avatar, then you may use a browser source along with Discord for voice detection. Select the one you want with the VoiceOver cursor. You’ll be dumped into a new window where you can name the new source. It will automatically be added to the currently selected scene. Press okay with the VoiceOver cursor at the bottom of the window. You’ll be moved to another window where you can set up the specifics. If adding images or media sources, it’s best if their resolution matches your stream resolution, otherwise it may not be centered or sized properly. This can be fixed quite easily if they don’t match up though. This is where there is no good way around it. If you want to position items on the screen (like an avatar or webcam view in the corner) then you’re going to need the assistance of a sighted person. You can resize the windows with the steppers, but positioning is beyond our ability at the time of writing. You may also come across combo boxes. You’ll have to use the same rigmarole as before: move the mouse cursor there, click, go into the new window with window chooser, find the option you want, move the mouse cursor there, click. Good to go. Press okay when you’re all done and your source will be added to the scene. When it comes to media sources like images and audio, I recommend to create an asset library with standardized names. I have a folder in my home directory. This makes it much easier to quickly swap out assets between streams by simply dropping in files and giving them the correct name.

## Working in the main OBS interface

So, you have a source. Maybe you have more than one source. Hopefully you got through it all. Let’s talk about the main window some more! I already mentioned some stuff in the interface description. Some items can be pressed with the VoiceOver cursor. Some items can be pressed with the mouse cursor. Rule of thumb: if `VO+Space` doesn’t work, use the mouse cursor and vice versa. If you come across a checkbox, assume it wants to murder you in your sleep and use the mouse cursor to check and uncheck it.
