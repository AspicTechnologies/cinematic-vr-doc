---
title: Automation
permalink: /cinematicvr/panner/Automation/
---

[first_project]: {{site.baseurl}}/cinematicvr/FirstProject/
[toolbar]: {{site.baseurl}}/cinematicvr/toolbar_video.png
[toolbar_grid]: {{site.baseurl}}/cinematicvr/toolbar_grid.png
[toolbar_transform]: {{site.baseurl}}/cinematicvr/toolbar_transform.png
[toolbar_move_tuto]: {{site.baseurl}}/cinematicvr/toolbar_move_tuto.gif
[toolbar_hold_tuto]: {{site.baseurl}}/cinematicvr/toolbar_hold_tuto.gif
[toolbar_draw_tuto]: {{site.baseurl}}/cinematicvr/toolbar_draw_tuto.gif

CinematicVR sound spatialization is based on automation. This can be define by a position on top of the video (aka azimtuh/elevation), and by focus (spread like).
Each channel is represented by a succesion of keyframes. Those keyframes can be manipulated using the mouse and by activating the correct options into the dedicated toolbar as well.

![toolbar][toolbar_video]

By default, toolbar buttons are (from left to right)

## Update transform

![Update transformation gui][toolbar_transform]
Select the area you want to use in your video. For instance, crop to use only one eye if your video is stereoscopic.

## Show grid

![Grid overview][toolbar_grid]
Display an elevation/azimuth grid overlay.

## Move/Mix Focus 

![Move keyframe][toolbar_move_tuto]
Also available with Tab key, switch the type of automation displayed.

## Draw keyframe

![Move keyframe with draw mode][toolbar_draw_tuto]
Add keyframes while video is playing using the mouse position. Usefull if you want to follow specific object with non linear mouvements.

## KeyFrame policy

![Ease/hold mode][toolbar_hold_tuto]
Define if keyframe is set to ease mode, with linear interpolation between two keyframes, or hold, jump to nextkeyframe without interpolation.
This option is set to ease mode by default.


## Read more

First project: [create an empty project and start spatialization][first_project] 

