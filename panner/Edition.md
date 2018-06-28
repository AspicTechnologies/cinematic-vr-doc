---
title: Edition
permalink: /cinematicvr/panner/Edition/
---

[automation_page]: {{site.baseurl}}/cinematicvr/panner/Automation
[strip_widget_page]: {{site.baseurl}}/cinematicvr/panner/StripWidget
[first_project]: {{site.baseurl}}/cinematicvr/FirstProject/

[toolbar]: {{site.baseurl}}/cinematicvr/img/toolbar_video.png
[toolbar_grid]: {{site.baseurl}}/cinematicvr/img/toolbar_grid.png
[toolbar_transform]: {{site.baseurl}}/cinematicvr/img/toolbar_transform.png
[toolbar_move_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_move_tuto.gif
[toolbar_hold_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_hold_tuto.gif
[toolbar_draw_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_draw_tuto.gif


Already presented in [automation page][automation_page], CinematicVR sound spatialization is based on automation. Automations can be modified by the mouse and by activating the correct options into the dedicated toolbar.

![toolbar][toolbar_video]

By default, toolbar buttons are (from left to right) 
	* Update transform
	* Show grid
	* Move / Mix Focus
	* Draw keyframe
	* Keyframe policy


## Update transform

![Update transformation gui][toolbar_transform]
Select the area you want to use in your video. For instance, crop to use only one eye if your video is stereoscopic.

## Show grid

![Grid overview][toolbar_grid]
Display an elevation/azimuth grid overlay to help you visualize where the automations are located.

## Move / Mix Focus 

![Move keyframe][toolbar_move_tuto]
Also available with Tab key, switch the type of automation displayed.
While using the move mode, you will be able to change position of any automation. While moving, video and sound are set to pause.
If the focus mode is used, the rendering of automation will change to allow the user to visualize the area and loudness (in db) of the sound object.

All of this informations are also available in the [strip widget][strip_widget_page] item.

## Draw keyframe

![Move keyframe with draw mode][toolbar_draw_tuto]
Add keyframes while video is playing using the mouse position. Usefull if you want to follow specific object with non linear mouvements.

## KeyFrame policy

![Ease/hold mode][toolbar_hold_tuto]
Define if keyframe is set to ease mode, with linear interpolation between two keyframes, or hold, jump to nextkeyframe without interpolation.
This option is set to ease mode by default.

## Read more

First project: [create an empty project and start spatialization][first_project] 

Automation: [explanation of Automation][automation_page] 

Strip widget: [explanation of strip widget][strip_widget_page] 
