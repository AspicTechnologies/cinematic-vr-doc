---
title: Panner presentation
permalink: /cinematicvr/PannerPresentation/
---

[window_full_num]: {{site.baseurl}}/cinematicvr/img/window_full_num.png



This page describes the various widgets and toolbars available in CinematicVR Panner.

_CinematicVR Panner screenshot_
![img CinematicVR Panner][window_full_num]

All widgets in the GUI can be moved and detached. Therefore, you are free to create your own setup. Currently, this setup is not saved when you close the software.

# 1. Video display

This is the central widget. It shows the video your are currently working on. It also diplays mono audio sources as colored dots and lets you move them to create position automation, etc.

Timeline:
* It is displayed below the video
* Time control:
	* Hit Spacebar to play/pause,
	* Hit Shift+Spacebar to stop (go back to the previous timecode)
* Moving the time cursor:
	* With your mouse, grab the cursor or click on the timeline
	* With Left and Right keys

Colored dots
* They are displayed for each mono source
* Moving source without "Draw" mode:
	* Grab an drag a dot to move its source
	* While moving, video is paused
	* When you release a dot, it creates a key-position
		* In "Interpolation" mode (default), behavior is to interpolate key-positions
		* In "Hold" mode, source position holds until next keyframe
* Moving source with "Draw" mode:
	* Grab an drag a dot to move its source
	* While moving, video keeps playing
	* Keyframes are created quickly while you drag the dot

* To edit key-positions, Right-Click on a dot, it allows you to :
	* Go to next or previous key
	* Delete current key
	* Choose between hold/interpolate
	* Create a new key that copies previous/next key position

Misc:
* Hit Tab button to switch to Mix Focus display
* Use "Show Grid" (in the toolbar) to display a grid overlay
* Use "Update Transform" (toolbar) to change displayed area
* You can hide the video using "Show video" (toolbar), it may help reduce CPU usage on small computers
* Use toolbars to switch to "Draw" mode and choose between "Interpolate"/"Hold"
* [Video codecs][codec_section] to learn how to install powerfull video codecs required by the Panner

# 2. Channels

This widget lists your channels (tracks). Each channel has:
* Name: double click to edit
* Type: 	
	* mono: a mono object will be spatialized using dynamic binaural rendering. 
	* ambisonics: from 1st to 3rd order, it uses 4, 9, 16 tracks.
	* stereo/native binaural: head-locked stereo track, not spatialized.
* Mute/Solo button: you can click and hold to mute/solo multiple channels.
* Render target:
	* Mono object can either be rendered as object (mono -> binaural) or as ambisonics (mono -> ambisonics)
	* No conversion is available for Ambisonics/Stereo channels.
* Show/Hide: this one is self-explainatory

Using the button at the bottom of the widget, you can add new channels. Use the small arrow to display all new channel variants.

# 3. Media sources

First field holds the path to your video file. You can change the video used by drag-n-dropping a file from your explorer. Once you have dropped a file, trigger play/pause to ensure video is loading.

At the bottom of the widget, buttons allow you to add file, asio or virtual sound card source. When mixing, you will mainly use asio or virtual soundcard, to connect with your DAW. However, for encoding a finallized project, you will have to use a bounced audio file.

Audio source can be renamed (double click). Use checkbox to chose which audio source is used by the audio renderer.

Each audio source displays a red or green sign. It turns to green if your channel layout matches your audio source (ie: they have the same amount of audio tracks). For instance, if I have two mono channels, a first order ambisonics and a stereo channel, my audio source must contain 8 tracks. As long as the sign is red, no sound is processed.

# 4. Monitor

* Render ambisonics order: if you have chosen to render mono objects as ambisonics, this field let you choose ambisonics order. For instance, you may choose to have 4 mono objects decoded to binaural at runtime, or send this 4 mono objects to ambisonics conversion.

* HRTF: currently deactivated, let you use your own HRTF (based on SOFA).

* Video stereo mode: use this field before launching monitoring to ensure your video will be properly displayed.

* Launch VR Monitor: opens a new program (CinematicVR Monitor) to display video in HMD and use head-tracking. You will have to activate MTC sync ("toolbar/Sync Master"). 

# 5. Channel strips

It displays more info about the channels selected in "Channels" widget.

* You can change channel color by clicking on the colored bar
* If you are playing, a vumeter is displayed under channel's name
* You can adjust azimuth/elevation for current key
* You can adjust Mix Focus for current key

# 6. Toolbars

By default, toolbar buttons are (from left to right):
* Transport
	* Play/Pause
	* Stop
	* Backward/forwad
	* Sync Master: activate/deactivate MTC emission
	* Show video: show/hide video
* Video/Automation
	* Update transform: select the area you want to use in your video. For instance, crop to use only one eye if your video is stereoscopic.
	* Show grid: display an elevation/azimuth grid overlay
	* Move / Mix Focus (also available with Tab key): switch the type of automation displayed

# 7. Preferences

Under "File/Preferences", you can tune various settings.

### Midi

* Midi in: the midi port that is used by CinematicVR Monitor to listen MTC
* Midi out count: number of midi out port (see below)
* Midi out: CinematicVR Panner will send MTC to this/these ports

### OSC

* OSC in port: CinematicVR Panner **will try to** listen for head-tracking on this port
* Used in port: CinematicVR Panner listens for head-tracking on this port (if OSC in port is already used by another app, Used in port is the first available port found on the computer)
* OSC out address: IP address of CinematicVR Monitor, in most case, use 127.0.0.1 for localhost
* OSC out port: ignore it

### Licensing

Path to license file. Set by Aspic Technologies Launcher app.

### Environment

Paths to Monitor and Encoder. Set by CinematicVR installer.

# 8. Others

* Animation timeline widget is under heavy work, and not very usefull in its ccurrent form. You may ignore/hide it.





