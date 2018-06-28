---
title: Media sources
permalink: /cinematicvr/panner/MediaSources/
---

[media_full]: {{site.baseurl}}/cinematicvr/img/media_full.png
[media_file_merge]: {{site.baseurl}}/cinematicvr/media_file_merge.gif

The source widget is the main widget related to any input media, such as audio or video.

![media source full][media_full]

Here is an overview of the media widget set with a video, and every available audio option.

## Video

If you want to add a video to your current project, simply drag and drop the file in this widget or use the browse button to select the video file. You can also use the Video menu and select "add video".

The video viewer widget will automatically resize to perfectly fit the video dimensions.

// todo lien vers codec

## Audio

The audio widget is composed by three audio input types: 
	* File input
	* Asio 
	* Virtual sound card
	
Each of them have common options such as "ready" feedback, delete and edit. Only the File input source have the export option.

### File input

The file input media source will let you configure your multiples audio inputs depending the number of channels you defined.

![media file input][media_file_merge]

In this example we defined two channels as object, each channel will correspond to one audio channel. After select file input option, a new window will show up, with the corresponding number of audio channel you need to set for this project. In this case two channels. Finally drag and drop your files to the correct channels, and merge.
The merge file will be saved and it will be reusable for further projects.

Please, ensure that every input files has the same sampling rate and the same bit depth.

### Asio


### Virtual sound card

CinematicVR Panner embeds Audiostack Virtual Soundcard. It means that when the *Panner* is launched, it will create an ASIO soundcard that can be detected and used by other software, such as Digital Audio Workstations. This virtual soundcard allows you to route audio signals between programs on the same computer.

We have added this virtual soundcard in CinematicVR so that you can keep audio editing in your DAW and stream tracks to the *Panner* for spatialization.

How do I use it?
- Prerequisties:
	- *CinematicVR* installed on your system
	- a DAW
- Launch *CinematicVR Panner*
	- In Audio sources panel, click "Add source from virtual driver"
	- You can adjust latency, samplerate and input count. You will also be able to modify this parameters later
	- Press Ok, soundcard is up and running

	![img Virtual soundcard dialog][vsc_config]

- Launch your DAW
	- Go to audio settings to find available ASIO devices
	- You should see a soundcard named "Audiostack"
- Connect audio
	- Route audio tracks from your DAW to Audiostack Virtual soundcard
	- Create channels in *CinematicVR Panner*
	- Spatialize!