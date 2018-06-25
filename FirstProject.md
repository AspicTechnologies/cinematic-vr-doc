---
title: First project
permalink: /cinematicvr/FirstProject/
---

[sync_guide]: {{site.baseurl}}/cinematicvr/PannerSync
[codec_section]: {{site.baseurl}}/cinematicvr/VideoCodecs

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
[toolbar_video]: {{site.baseurl}}/cinematicvr/img/toolbar_video.png
[VSC1]: {{site.baseurl}}/cinematicvr/img/asio/audiostack_virtualsoundcard.jpg
[reaper_route1]: {{site.baseurl}}/cinematicvr/img/asio/reaper_routing1.jpg
[reaper_route2]: {{site.baseurl}}/cinematicvr/img/asio/reaper_routing2.jpg
[reaper_route3]: {{site.baseurl}}/cinematicvr/img/asio/reaper_routing3.jpg

This tutorial will help you create a simple project using your DAW and our Panner on the same computer. We will see how to :
* configure the Panner according to this first workcase
* stream audio from your DAW to the Panner using Audiostack virtual soundcard 
* configure synchronization
* spatialize a first session within CinematicVR Panner. 

We will not cover every menu and feature encountered, please refer to the full documentation for details.

# Prerequisties
* CinematicVR is installed
* You own a valid license (ex: a free trial license)
* You have a DAW session with various tracks (mono, ambisonics, stereo)	
* You have installed a video codec pack (see [dedicated section][codec_section])

# Tutorial

First, launch CinematicVR Panner

## 1. Check preferences

To ensure your synchronization will work, check our [Sync guide][sync_guide]

OSC, licensing and environment defaults should work.

## 2. Create a new project with 360-video

Choose File/Create new empty project.

Locate "Media sources" widget (see screenshot)

Drag and drop a video file from your explorer to the first field of this widget.

_Drag and drop video file_
![img Preferences][tuto_video_file]

In toolbar, choose "Update transform". This will display the video and a red-bordered frame. In the new small window, you have to set video size, for instance 4096x1024 without offset. If your video is stereoscopic, these fields will help you define the area of the video you want to work with.

_Choose displayed area_
![img Preferences][tuto_video_size]

Check that the video is playing by hitting play button (or your spacebar). If not, available codecs on your system cannot decode your video file. Please read our [dedicated section][codec_section].

## 3. Create audio layout

Add audio objects in "Channels" widget: you can add mono objects, ambisonics (1st to 3rd order), stereo/native binaural. If you create a mono object, set its "render target" to Object to get precise binaural rendering. If you want to use object-to-ambisonics conversion, please read advanced documentation.

_Channels widget_
![img Preferences][tuto_channels]

_Setting render target on mono objects_
![img Preferences][tuto_channels_render]

Each type of channel has a different audio channel count: 1 for a mono object, 4 for a 1st order ambisonics, 16 for a third order ambisonics, 2 for a head-locked. 

Create an asio source: in "Media sources" widget, click "Add source from virtual driver" and let the dialog fill information for you. You will see that CinematicVR Panner automatically assigns asio inputs to your channels.

![img Virtual sound card][VSC1]

## 4. Configure your DAW

In your DAW, route your tracks to Audiostack Asio driver. 

For instance, I have CinematicVR and Reaper session with 1 stereo track, then 1 mono object, then 1 first order ambisonics. In reaper, I'll route my audio this way:

![img Preferences][reaper_route1]
![img Preferences][reaper_route2]
![img Preferences][reaper_route3]

Configure MTC chasing in your DAW using our [Sync guide][sync_guide].

Don't forget to start audio sync with the DAW checking "Sync master" and to start MTC Chasing in your DAW.

![img Preferences][toolbar_mtc]

Check that audio is properly transmitted from DAW to Panner, processed and audible (hitting play button or spacebar). If not, check MTC sync and Asio config.

## 5. Move audio sources

You can now move audio sources (mono objects only) by clicking colored dots on the video widget.

![img Preferences][toolbar_video]

Automation system is based on key-positions. Keyframes provide interpolation to smooth movements; they also come with a "Draw" mode for fast moving sources. Please consult advanced section of the doc to learn more about keyframing and tracking your audio sources.

## 6. Monitor in VR

At this point, you are listening to audio that is not yet connected to head-tracking. Go to "Audio monitor" widget, ignore options for this tuto, and hit "Launch VR Monitoring".

If you have a HTC Vive or Oculus CV1 plugged and ready, it will display the video and use head-tracking to drive audio spatialization. Otherwise, you may use your mouse (hold right click) to rotate camera in CinematicVR Monitor.

_Monitor widget_
![img Preferences][tuto_monitor]

