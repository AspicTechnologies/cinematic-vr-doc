---
title: Custom audio format
permalink: /cinematicvr/CustomAudioFormat/
---

[cvr_player_screen]: {{site.baseurl}}/cinematicvr/img/cvr_player_screen_1.jpg

For precise audio spatialization, reduced channel count and incresed interactivity, we have decided to provide our own open format. 

This format is based on readable metadata stored in a json-formatted file (.asatl), and audio streams stored as an ogg-compressed audio file. 

Screenshot of the Unity3D plugin available in CinematicVR Player 
![img CinematicVR Player Unity plugin][cvr_player_screen]

# Object based, Scene based, Channel based audio

Our own format combines Object based audio (mono sources with realtime binaural rendering), Scene based audio (ambisonics) and channel based audio (head-locked binaural).

It allows our users to get the most of spatial audio: objects for precise audio sources, ambisonics for rich audio environments; while keeping a rational audio channel count. For instance, we often use 4 objects, a first order ambisonics and a head-locked stereo streams. It fits in 10 audio channels.

Object are stored as mono streams that can be processed according to the user interaction such as [Mix Focus](#Mix focus)

# Unity integration

The .asatl file can be imported in Unity through our SDK. The importation process creates AnimationClip in Unity that are directly associated with the corresponding Game Objects.

This feature is particularly useful to imagine workflows between av production and videogame combining linear narratives and interactions. 

# Gaze-based interaction

## Mix focus
Mix focus is a gaze-based interaction that controls a object stream gain according to the angle between the object direction and the gaze direction. 

This gain correction is defined by the mixer as an additional automation and can be positive or negative.

