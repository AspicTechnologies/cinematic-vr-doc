---
title: Sync guide
permalink: /cinematicvr/PannerSync/
---

[midi1]: {{site.baseurl}}/cinematicvr/img/sync/midi1.jpg
[midi_loopback_sample]: {{site.baseurl}}/cinematicvr/img/sync/midi1.jpg
[midi_reaper]: {{site.baseurl}}/cinematicvr/img/sync/midi_reaper.jpg
[midi_reaper2]: {{site.baseurl}}/cinematicvr/img/sync/midi_reaper2.jpg
[midi_reaper3]: {{site.baseurl}}/cinematicvr/img/sync/midi_reaper3.jpg
[midi2]: {{site.baseurl}}/cinematicvr/img/sync/midi2.jpg

For a seamless integration within audiovisual workflows, *CinematicVR Panner* must be synchronized with your Digital Audio Workstation. To do that, the software relies on Midi Time Code (MTC) sent from one software to the other.

A typical CinematicVR setup will look like this:
- *Panner*: timecode Master
- *Monitor*: timecode Slave
- DAW: timecode Slave

There is several way to communicate Midi between CinematicVR and the Digital Audio Workstation. We have already tested the following configuration succesfully:
- Midi over IP using [Rtp Midi](https://en.wikipedia.org/wiki/RTP-MIDI){:target="_blank"} on both Apple and Windows ([Rtp Midi for Windows](https://www.tobias-erichsen.de/software/rtpmidi.html){:target="_blank"})
- Midi loopback using [LoopBeOne](http://www.nerds.de/en/loopbe1.html){:target="_blank"}
- Midi compatible card on both computer with a Midi link between them,
- Midi within a MADI connection (this configuration handles audio and synchronization with the same link)


## MTC principle
MTC message are Sysex midi messages. At each quarter frame, a eighth of the timecode is sent so that a complete SMPTE timecode is received every 2 frames.

When seeking over the session an other type of message is sent containing the complete timecode.

## CinematicVR Panner Midi setup

Launch *CinematicVR Panner*.

In **File > Preferences**, reach for the Midi tab.

![img Home page][midi1]

- **Midi in** port is used by the *Monitor* to listen to MTC on this port. If the *Panner* is configured as Slave, it will also listen for incoming MTC sync.

- **Midi out count** specifies the number of midi out port.

- **Midi out** ports will be used when the *Panner* is configured as Master. *Panner* will send MTC to every midi out port.

In *CinematicVR Panner*, activate MTC sync using the clock button. The dropdown menu allows you to chose between Master and Slave. *Note: only Master is currently available.*

-------

<br/>

## Typical setups

### 1. CinematicVR and DAW on the same computer

You need:
- a Midi loopback (consider using LoopBeOne)

In the *Panner*, under File/Preferences/Midi:
- **Midi in**: midi loopback in
- **Midi out count**: 1
- **Midi out**: midi loopback out

![img Home page][midi_loopback_sample]

Dont forget to enable sync Master in the *Panner*

In your DAW:
- Listen to midi loopback in

How it works:
- the *Panner* sends MTC to "midi loopback out"
- midi loopback copies the MTC it receives on "midi loopback out" back to "midi loopback in"
- your DAW listens to "midi loopback out" to sync audio
- the *Monitor* listens to "midi loopback out" to sync video


### 2. CinematicVR on Windows, DAW on another computer (Windows or MacOS)

You need:
- a Midi loopback (consider using LoopBeOne)
- a Midi link between computers (consider using a virtual network midi driver such as RtpMidi or a hardware link)

In the *Panner*, under File/Preferences/Midi:
- **Midi in**: midi loopback in
- **Midi out count**: 2
- **Midi out**: 
	- midi loopback out
	- midi link to remote computer

![img Midi tab for remote MTC][midi2]

Dont forget to enable sync Master in the *Panner*

In your DAW, on another computer:
- Listen to midi link (either a virtual midi driver connected to your CinematicVR station or a hardware link)

How it works:
- the *Panner* sends MTC to "midi loopback out" and "midi link"
- midi loopback copies the MTC it receives on "midi loopback out" back to "midi loopback in"
- the *Monitor* listens to "midi loopback out" to sync video
- your DAW listens to "midi link" to sync audio

-------

<br/>

## Specific MTC setup

### 1. MTC in Reaper

In Reaper, right-click on the play button, it will open the "External Timecode Synchronization".

Check "Enable synchronization to timecode"

In the "Use input" list, choose your a MTC input port. In most of our samples, we choose "MTC: LoopBe Internal Midi" since the *Panner* outputs on LoopBeOne.

![img Home page][midi_reaper]

Close the dialog, and hit play. This button should turn green and the timecode indicator to [Waiting for TC].

![img Home page][midi_reaper2]

In the *Panner*, check "sync Master" and hit play, Reaper should start receiving timecode and play your audio!

![img Home page][midi_reaper3]

If you have the feeling that something is not working:
- restart Reaper to ensure it reloads available Midi drivers,
- check that the *Panner* is configured as "Sync Master"
- check that the *Panner* is playing (with at least one channel and a valid source)
- contact us for support!

### 2. MTC in Protools

### 3. Configuring RtpMidi