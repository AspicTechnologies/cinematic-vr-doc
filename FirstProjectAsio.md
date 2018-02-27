---
title: Your first DAW-based project
permalink: /cinematicvr/PannerFirstProjectAsio/
---

[license_link]: {{site.baseurl}}/cinematicvr/Installation
[video_link]: {{site.baseurl}}/cinematicvr/TODO

[prefs_screen]: {{site.baseurl}}/cinematicvr/img/tuto_prefs.png
[tuto_prefs_midi_2]: {{site.baseurl}}/cinematicvr/img/tuto_prefs_midi_2.png
[prefs_osc_screen]: {{site.baseurl}}/cinematicvr/img/tuto_prefs_osc.png
[tuto_video_file]: {{site.baseurl}}/cinematicvr/img/tuto_media_video.png
[tuto_video_size]: {{site.baseurl}}/cinematicvr/img/tuto_media_video_size.png
[tuto_audio_file_source]: {{site.baseurl}}/cinematicvr/img/tuto_audio_file_source.png
[tuto_channels]: {{site.baseurl}}/cinematicvr/img/tuto_channels.png
[tuto_audio_file_source_check]: {{site.baseurl}}/cinematicvr/img/tuto_audio_file_source_check.png
[tuto_channels_render]: {{site.baseurl}}/cinematicvr/img/tuto_channels_render.png
[tuto_monitor]: {{site.baseurl}}/cinematicvr/img/tuto_monitor.png
[tuto_asio]: {{site.baseurl}}/cinematicvr/img/tuto_asio.png
[toolbar_mtc]: {{site.baseurl}}/cinematicvr/img/toolbar_mtc.png


This tutorial will help you create a simple project using your DAW and our Panner. We will see how to :
* to configure the Panner according to this first workcase
* stream audio from your DAW to the Panner using Asio soundcard (including audio over IP), 
* to configure synchronization
* to spatialize a first session within CinematicVR Panner. 

We will not cover every menu and feature encountered, please refer to the full documentation for details.

{% icon fa-exclamation-triangle  %} We advise you to make regular save of your projects, by hitting Ctrl+S or under File/Save.

# Prerequisties
* CinematicVR is installed
* You own a valid license (ex: a free trial license),
* You have a DAW session with various tracks (mono, ambisonics, stereo),
* You have ASIO link capabilites between the DAW and CinematicVR (for instance an audio over IP setup or soundcards with enough I/O).
	
# Tutorial

First, launch CinematicVR Panner

## 1. Check preferences

Under File/Preferences, go to tab Environment and check if you have set the path to:
* license_file: Path to a valid .aslc file.
* vrplayer_path: Path to the CinematicVR_Monitor.exe (Usually C:/Program Files/Aspic Technologies/CinematicVR/Monitor/CinematicVR_Monitor.exe)

Other fields such as asatl_encoder or ffmpeg can be ignored.

_Settings/Environment_
![img Preferences][prefs_screen]

In Midi tab, set Midi out count to 2, select a Midi In port and select two midi out ports.

One Midi out port  will be used to sync video player (CinematicVR Monitor) and the other one Midi will be used to drive your DAW.

You can use virtual midi drivers to help you setup your session.

_Settings/Midi_
![img Preferences][tuto_prefs_midi_2]

In OSC tab, select in and out ports, and set osc out address to 127.0.0.1 (localhost)
OSC out port will be used to send automation (audio sources position, focus) to the Monitor or one of your application. OSC in port will listen to incoming head-tracking data.

_Settings/OSC_
![img Preferences][prefs_osc_screen]

## 2. Create a new project with 360-video

Choose File/Create new empty project.

Locate "Media sources" widget (see screenshot)

Drag and drop a video file from your explorer to the first field of this widget.

_Drag and drop video file_
![img Preferences][tuto_video_file]

In toolbar, choose "Update transform". This will display the video and a red-bordered frame. In the new small window, you have to set video size, for instance 4096x1024 without offset. If your video is stereoscopic, these fields will help you define the area of the video you want to work with.

_Choose displayed area_
![img Preferences][tuto_video_size]

Check that the video is playing by hitting play button (or your spacebar). If not, available codecs on your system cannot decode your video file. Please read our [dedicated section][video_link].

## 3. Create audio layout

Add audio objects in "Channels" widget: you can add mono objects, ambisonics (1st to 3rd order), stereo/native binaural. If you create a mono object, set its "render target" to Object to get precise binaural rendering. If you want to use object-to-ambisonics conversion, please read advanced documentation.

_Channels widget_
![img Preferences][tuto_channels]

_Setting render target on mono objects_
![img Preferences][tuto_channels_render]

Each type of channel has a different audio channel count: 1 for a mono object, 4 for a 1st order ambisonics, 16 for a third order ambisonics, 2 for a head-locked. 

Create an asio source: in "Media sources" widget, click "Add asio source" and browse available drivers. You will see that CinematicVR Panner automatically assigns asio inputs to your channels.

If this mapping doesn't fit your need, you can edit each association individually.

![img Preferences][tuto_asio]

To start audio sync with the DAW, check "Sync master" and start MTC Chasing in your DAW.

![img Preferences][toolbar_mtc]

Check that audio is properly transmitted from DAW to Panner, processed and audible (hitting play button or spacebar). If not, check MTC sync and Asio config.

## 4. Move audio sources

You can now move audio sources (mono objects only) by clicking colored dots on the video widget.

Default automation system is based on key-positions. Therefore, you have to click and hold, then release the source where you want it to be at one moment. Automation engine will interpolate positions between key-positions (spherical interpolation is used). Therefore, if one character is moving in your video, you can specify his/her position at regular intervals and let interpolation smooth his/her movement.

## 5. Monitor in VR

At this point, you are listening to audio that is not yet connected to head-tracking. Go to "Audio monitor" widget, ignore options for this tuto, and hit "Launch VR Monitoring".

If you have a HTC Vive or Oculus CV1 plugged and ready, it will display the video and use head-tracking to drive audio spatialization. Otherwise, you may use your mouse (hold right click) to rotate camera in CinematicVR Monitor.

_Monitor widget_
![img Preferences][tuto_monitor]

