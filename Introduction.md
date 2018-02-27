---
title: Introduction
permalink: /cinematicvr/Introduction/
---

[cvr_panner_screen]: {{site.baseurl}}/cinematicvr/img/cvr_panner_screen_1.jpg
[cvr_player_screen]: {{site.baseurl}}/cinematicvr/img/cvr_player_screen_1.jpg
[cvr_monitor_screen]: {{site.baseurl}}/cinematicvr/img/cvr_monitor_screen_1.jpg


CinematicVR by Aspic Technologies is a software suite dedicated to 360 audio. It is composed of a 360 panner, a VR monitor, a SDK for custom audio player. These components will be described more precisely in this documentation.

# Concepts 

Lets discover the three main components:
* [Panner](#panner)
* [Monitor](#monitor)
* [Player](#player)

## Panner

CinematicVR Panner is a 360 standalone audio panner. This software allows you to record audio sources movement on a 360 video, hear the binaurally rendered sound and perform various encoding.

The panner can handle audio streams incoming from your favorite DAW or from a bounced audio file.

The embedded encoders can create various spatialized audio formats such as TBE, ADM, HOA files (Ambix up to third order) or our own format. Our own format combines objects and ambisonics streams and allow some gaze-based interaction (ex: Mix focus).

Monitoring is performed through realtime binaural rendering of your work controlled by head tracking of your HMD (using our VR Monitor) or external tracking through OSC.

Screenshot of CinematicVR Panner

![img CinematicVR Panner][cvr_panner_screen]

---

## Monitor

CinematicVR Monitor is a VR application. Synchronized with our Panner, it will display your 360 video using an Oculus CV1 or a HTC Vive. Without such a headset you will be able to pan the video around in a simple flat window.

This monitor will send head-tracking to the Panner to drive binaural rendering.

Representation of CinematicVR Monitor
![img CinematicVR Panner][cvr_monitor_screen]

---

## Player

CinematicVR Player SDK contains our rendering software library and plugins that help developers get spatial audio in their VR/AR/MR/360 applications.

Whether your spatial audio has been created by a third party tool or with ours, our Player is able to read it.

It is available as a cross-platform C/C++ library (windows, linux, android) and plugins (Unity3D). Our player is not only a bunch of audio filters. It also reads and outputs audio: we use low-level audio APIs (Asio, Core audio, OpenSL, ...) to ensure best latencies. 

