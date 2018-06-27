---
title: Automation
permalink: /cinematicvr/panner/Automation/
---

[edition_page]: {{site.baseurl}}/cinematicvr/panner/Edition
[strip_widget_page]: {{site.baseurl}}/cinematicvr/panner/StripWidget


CinematicVR sound spatialization is based on automation. An automation is represented by a succesion of keyframes. It defines the position of a sound object by using a colored dot on top of the video. Automations are defined by two parameters, the position and the mixfocus.

## Parameters

### Position

The position of a keyframe define the origin of the sound object. This position is defined by using azimuth and elevation. 
It´s represented by a colored dot on top of the video.

### MixFocus

What we call MixFocus correspond to the area where the sound can be heard. The mixfocus is defined by three parameters, radius, gain at center and gain on border.
Radius correspond to the area width, represented by a circle. Gain at center set the sound level of the object at the center of the circle, while gain on border set the sound level on border. Between center and border, the sound level will be defined by a linear interpolation of the two gains.


Depending of the channel type represented by the automations, position and MixFocus cannot be set.

| Automation type | Position | MixFocus |
|-----------------|----------|----------|
| Object    | ✔ | ✔ |
| Ambisonic | ✔ | ✖ |
| Head-lock | ✖ | ✖ |

* Object is a mono source, then its position and mixfocus can be defined
* Ambisonic position can be set but not the mixfocus due to it´s spatialization.
* Head-lock stereo, both parameters cannot been modified.

## Keyframe

### Interpolation mode

There is two interpolation mode. The first one is the linear interpolation, named Ease mode. Between two keyframe, CinematicVR will compute a virtual keyframe using a linear interpolation by using the position of previous and next keyframe. The second mode is named hold mode. It enforce the non interpolation between two keyframes. The hold mode is useful, by example, if there is a video cut and object sounds position changed. You can use one keyframe with the hold mode before the cut frame, and correctly place the next keyframe. Hold mode is used for transport the keyframe.


### Edition mode

KeyFrame can be moved by using two different modes. The "classic" mode, will allow the user to move the keyframe while the video is paused, this can be useful if the object you want to follow is static.
The other mode, named "draw", is a real time keyframe displacement. The use case, by example, is when you want to track someone moving. By enable the draw mode you will be able to place the keyframe while the video is playing.


## Read more

Keyframe edition : [edit keyframes][edition_page]
Strip widget : [strip widget options][strip_widget_page]
