---
title: Audio
permalink: /cinematicvr/panner/AudioSources/
---

[media_full]: {{site.baseurl}}/cinematicvr/img/media_full.png
[encoders]: {{site.baseurl}}/cinematicvr/Encoder/
[media_file_merge]: {{site.baseurl}}/cinematicvr/media_file_merge.gif

The source widget is the main widget related to any input media, such as audio or video.

![media source full][media_full]

Here is an overview of the media widget set with a video, and every available audio option.

The audio widget is composed by three audio input types: 
	* File input
	* Asio 
	* Virtual sound card
	
Each of them have common options such as "ready" feedback, delete and edit. Only the File input source have the export option, related to [encoders][encoders].

## File input

The file input media source will let you configure your multiples audio input files depending the number of channels you defined. If you want to export your project you will have to use file input. Only this input type can export CinematicVR projects.

![media file input][media_file_merge]

How do I use it?
- Prerequisties:
	- *CinematicVR* installed on your system
- Launch *CinematicVR Panner*
	- In Audio sources panel, click "Add file source"
	- Drag and drop corresponding files to the corrects channel
	- Press merge
	- Save merged file
	
Please, ensure that every input files has the same sampling rate and the same bit depth.

## Asio

// TODO

## Virtual sound card

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
	
	
## Read more

Synchronization guide: [how to sync *Panner* and DAWs timelines][sync_guide] 

First project: [create an empty project and start spatialization][first_project] 

Encoders: [how to export a project][encoders] 