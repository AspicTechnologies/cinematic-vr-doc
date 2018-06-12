---
title: Glossary
permalink: /cinematicvr/Glossary/
---

[intro_page]: {{site.baseurl}}/cinematicvr/Introduction/
[VSC]: {{site.baseurl}}/cinematicvr/panner/VirtualSoundCard/



### Panner
CinematicVR Panner is a standalone application for Windows. It is a 360 audio panner, compatible with any DAW thanks to MTC sync, ASIO support and a Virtual soundcard.

To learn more, see [Doc introduction][intro_page].

### Monitor
CinematicVR Monitor is a standalone VR application for Windows. It displays 360 videos (mono and stereoscopic) in your HMD. It sends head tracking through OSC to drive spatialization algorithms in *Panner*. Its video playback is synchronized using MTC.

To learn more, see [Doc introduction][intro_page].

### Player
CinematicVR Player is a standalone VR application for Windows. It reads various audio and video formats, especially those exported from *CinematicVR Panner* (TBE, Ambx, Aspic, ...)

To learn more, see [Doc introduction][intro_page].

### Player SDK 
CinematicVR Player SDK is a software development kit. It allows third party developers to create their own player for platform such as Android, Linux, Windows. It embeds any feature included in CinematicVR products: ASIO support, Spatialization algorithms, Ambisonics codecs, MTC synchronization, ...

To learn more, see [Doc introduction][intro_page].

### Virtual soundcard
Virtual soundcard are softwares that behave like real soundcard, without any hardware plugged to your system. Many of them are used to stream audio between multiple computers without physical link (Audio over IP such as AES67, Dante, ...). Other virtual soundcards are designed to allow multiple programs to share audio (Jack, Audiostack virtual soundcard, ...).

To learn more, see [Audiostack virtual soundcard][VSC]



