---
title: Virtual Soundcard
permalink: /cinematicvr/panner/VirtualSoundCard/
---

[sync_guide]: {{site.baseurl}}/cinematicvr/PannerSync/
[first_project]: {{site.baseurl}}/cinematicvr/FirstProject/
[vsc_config]: {{site.baseurl}}/cinematicvr/img/asio/audiostack_virtualsoundcard.jpg

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

