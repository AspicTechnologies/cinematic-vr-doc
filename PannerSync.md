---
title: Sync guide
permalink: /cinematicvr/PannerSync/
---

Work in progress

For a seamless integration within audiovisual workflows, Cinematic VR Panner must be synchronized with the Digital Audio Workstation. To do that the software relies on Midi Time Code sent from one software to the other.

There is several way to communicate Midi between Cinematic VR and the Digital Audio Workstation. We have already tested the following configuration succesfully.

- Midi compatible card on both computer with a Midi link between them
- Midi within a MADI connection (this configuration handled audio and synchronization with the same link)
- Midi over IP using Rtp Midi (TODO link to rtp midi standard Apple)

In this part of the documentation, the configuration of a synchronization link with RTP midi will be explained.

## MTC principle
MTC (TODO link to MTC wikipedia page) message are Sysex midi messages. At each quarter frame a eighth of the timecode is sent so that a complete SMPTE timecode is received every 2 frames.

When seeking over the session an other type of message is sent containing the complete timecode.

## Cinematic VR as master 


### Setting up Cinematic VR
First be sure that a software handling RTP midi is installed.

In file > preferences reach for the Midi tab.

In Midi tab, set Midi out count to 2, select a Midi In port and select two midi out ports.

One Midi out port  will be used to sync the video player (CinematicVR Monitor) and the other one Midi will be used to drive your DAW. This second one should have the RTP midi driver name.

Press 'Ok' to accept the configuration change.

On the main toolbar, check "Sync master". MTC messages are now sent when playing and seeking.

### Setting up Protools as client

### Setting up Reaper as client