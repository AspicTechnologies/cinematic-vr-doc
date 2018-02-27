---
title: Your first file-based project
permalink: /cinematicvr/PannerFirstProjectFile/
---

[license_link]: {{site.baseurl}}/cinematicvr/Installation
[video_link]: {{site.baseurl}}/cinematicvr/TODO

[prefs_screen]: {{site.baseurl}}/cinematicvr/img/tuto_prefs.png
[prefs_midi_screen]: {{site.baseurl}}/cinematicvr/img/tuto_prefs_midi.png
[prefs_osc_screen]: {{site.baseurl}}/cinematicvr/img/tuto_prefs_osc.png
[tuto_video_file]: {{site.baseurl}}/cinematicvr/img/tuto_media_video.png
[tuto_video_size]: {{site.baseurl}}/cinematicvr/img/tuto_media_video_size.png
[tuto_audio_file_source]: {{site.baseurl}}/cinematicvr/img/tuto_audio_file_source.png
[tuto_channels]: {{site.baseurl}}/cinematicvr/img/tuto_channels.png
[tuto_audio_file_source_check]: {{site.baseurl}}/cinematicvr/img/tuto_audio_file_source_check.png
[tuto_channels_render]: {{site.baseurl}}/cinematicvr/img/tuto_channels_render.png
[tuto_monitor]: {{site.baseurl}}/cinematicvr/img/tuto_monitor.png


This tutorial will help you create a simple project, based on a bounced audio-file. Whether it is probably not the most interesting use-case, it will help you understand CinematicVR Panner features.
We will not cover in details every menu and feature encountered, please refer to full documentation.

# Prerequisties
* CinematicVR is installed
* You own a license
* You have a multi-channel audio file

	Ideally, this WAV file (48kHz, 16bits) contains at least one mono object, one ambisonics (1st, 2nd or 3rd order) and one stereo stream.
	
If you don't have CinematicVR or don't own any license, refer to [Installation][license_link].

# Tutorial

First, launch CinematicVR Panner

## 1. Check preferences

Under File/Preferences, go to tab Environment and check if you have set the path to:
* license_file: Path to a valid .aslc file.
* vrplayer_path: Path to the CinematicVR_Monitor.exe (Usually C:/Program Files/Aspic Technologies/CinematicVR/Monitor/CinematicVR_Monitor.exe)

Other fields such as asatl_encoder or ffmpeg can be ignored.

_Settings/Environment_
![img Preferences][prefs_screen]

In Midi tab, select a Midi In port, set Midi out count to 1, and select a Midi out port.

This two midi ports will be used to synchronize Panner with Monitor. You can use a virtual midi driver to create a midi loopback on your computer. If you setup a mixing session with two computers, you can use midi provided by your soundcards.
If your not familiar with midi and virtual midi driver; you can take a look at LoopBe1, a fine software with a 30 days trial period.  

_Settings/Midi_
![img Preferences][prefs_midi_screen]

In OSC tab, select in and out ports, and set osc out address to 127.0.0.1 (localhost)
OSC out port will be used to send automation (audio sources position, focus) to Monitor. OSC in port will listen to incmoing head-tracking data.

_Settings/OSC_
![img Preferences][prefs_osc_screen]

## 2. Create a new project with 360-video

Chose File/Create new empty project.

Locate "Media sources" widget (see screenshot)

Drag and drop a video file from your explorer to the first field of this widget.

_Drag and drop video file_
![img Preferences][tuto_video_file]

In toolbar, choose "Update transform". This will display the video and a red-bordered frame. In the new small window, you have to set video size, for instance 4096x1024 without offset. If your video is stereoscopic, these fields will help you define the area of the video you want to work with.

_Chose displayed area_
![img Preferences][tuto_video_size]

Check that the video is playing by hitting play button (or your spacebar). If not, available codecs on your system cannot decode your video file. Please read our [dedicated section][video_link].

## 3. Create audio layout

Create an audio file source: in "mEdia sources" widget, click "Add file source" and browse for an audio file. 
This file must contain all the tracks you want to use, for instance a bounced output of a mixing session. 
Ideally, this file will contain one mono track, on ambisonics track and one stereo track. It must be .Wav, 16bits, @48kHz.

_Media sources widget_
![img Preferences][tuto_audio_file_source]

Add audio objects in "Channels" widget: you can add mono objects, ambisonics (1st to 3rd order), stereo/native binaural. If you create a mono object, set its "render target" to Object to get precise binaural rendering. If you want to use ambisonics encoding/decoding, please read advanced documentation.

_Channels widget_
![img Preferences][tuto_channels]

_Setting render target on mono objects_
![img Preferences][tuto_channels_render]

Each type of channel has a different audio channel count: 1 for a mono object, 4 for a 1st order ambisonics, 16 for a third order ambisonics, 2 for a head-locked. Please add tracks that match with the audio file you selected (same amount of channels). Once this equality is reached, you audio source will display a green sign.

As long at the number of channels doesn't match, no audio is processed in CinematicVR Panner. When the active audio source goes to green, audio is ready to play.

_Audio source is ready_
![img Preferences][tuto_audio_file_source_check]

Check that your audio is processed and audible by hitting play button or spacebar. If not, check that channels and audio source are consistent.

## 4. Move audio sources

You can now move audio sources (mono objects only) by clicking colored dots on the video widget.

Default automation system is based on key-positions. Therefore, you have to click and hold, then release the source where you want it to be at one moment. Automation engine will interpolate positions between key-positions. Therefore, if one character is moving in your video, you can specify his/her position at regular intervals and let interpolation smooth his/her movement.

## 5. Monitor in VR

At this point, you are listening to audio that is not yet connected to head-tracking. Go to "Audio monitor" widget, ignore options for this tuto, and hit "Launch VR Monitoring".

If you have a HTC Vive or Oculus CV1 plugged and ready, it will display the video and use head-tracking to drive audio spatialization. Otherwise, you may use your mouse (hold right click) to rotate camera in CinematicVR Monitor.

_Monitor widget_
![img Preferences][tuto_monitor]

