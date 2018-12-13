---
title: Edition
permalink: /cinematicvr/panner/Edition/
---

[automation_page]: {{site.baseurl}}/cinematicvr/panner/Automation
[strip_widget_page]: {{site.baseurl}}/cinematicvr/panner/StripWidget
[first_project]: {{site.baseurl}}/cinematicvr/FirstProject/
[page_edition_panner]: {{site.baseurl}}/cinematicvr/Edition/#Panner

[toolbar]: {{site.baseurl}}/cinematicvr/img/toolbar_video.png
[toolbar_grid]: {{site.baseurl}}/cinematicvr/img/toolbar_grid.png
[toolbar_transform]: {{site.baseurl}}/cinematicvr/img/toolbar_transform.png
[toolbar_move_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_move_tuto.gif
[toolbar_hold_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_hold_tuto.gif
[toolbar_draw_tuto]: {{site.baseurl}}/cinematicvr/img/toolbar_draw_tuto.gif
[strip_widget_position]: {{site.baseurl}}/cinematicvr/img/strip_widget_position.png
[strip_widget_mixfocus]: {{site.baseurl}}/cinematicvr/img/strip_widget_mixfocus.png
[strip_widget_overview]: {{site.baseurl}}/cinematicvr/img/strip_widget_overview.png
[pie_menu_overview]: {{site.baseurl}}/cinematicvr/img/pie_menu_overview.png
[pie_menu_alt_overview]: {{site.baseurl}}/cinematicvr/img/pie_menu_alt_overview.png
[keyframe_remove_overview]: {{site.baseurl}}/cinematicvr/img/keyframe_remove_overview.png
[keyframe_move_overview]: {{site.baseurl}}/cinematicvr/img/keyframe_move_overview.png

## Panner 

Already presented in [automation page][automation_page], CinematicVR sound spatialization is based on automation. Automations can be modified by the mouse and by activating the correct options into the dedicated toolbar.

![toolbar][toolbar_video]

By default, toolbar buttons are (from left to right) 
	* Update transform
	* Show grid
	* Move / Mix Focus
	* Draw keyframe
	* Keyframe policy


### Update transform

![Update transformation gui][toolbar_transform]
Select the area you want to use in your video. For instance, crop to use only one eye if your video is stereoscopic.

### Show grid

![Grid overview][toolbar_grid]
Display an elevation/azimuth grid overlay to help you visualize where the automations are located.

### Move / Mix Focus 

![Move keyframe][toolbar_move_tuto]
Also available with Tab key, switch the type of automation displayed.
While using the move mode, you will be able to change position of any automation. While moving, video and sound are set to pause.
If the focus mode is used, the rendering of automation will change to allow the user to visualize the area and loudness (in db) of the sound object.

All of this informations are also available in the [strip widget][strip_widget_page] item.

### Draw keyframe

![Move keyframe with draw mode][toolbar_draw_tuto]
Add keyframes while video is playing using the mouse position. Usefull if you want to follow specific object with non linear mouvements.

### KeyFrame policy

![Ease/hold mode][toolbar_hold_tuto]
Define if keyframe is set to ease mode, with linear interpolation between two keyframes, or hold, jump to nextkeyframe without interpolation.
This option is set to ease mode by default.

## Strip widget

Automations can be edited by using [toolbar][page_edition_panner], but also by using strip widgets. As said in [automation][page_automation] presentaion page, there is three type of channel :
	- object
	- ambisonics
	- head-lock
	
Strip widget will be rendered depending of this type, related to available options :

![strip widget][strip_widget_overview]

| Automation type | Position | MixFocus |
|-----------------|----------|----------|
| Object    | ✔ | ✔ |
| Ambisonic | ✔ | ✖ |
| Head-lock | ✖ | ✖ |

### Vu meter

Strip widget contains a small bar, named volume unit meter, displaying a representation of the signal level for the current channel played. 
It can be composed by multiple sub bar, depending the number of sub-channels.

### Position controls

![strip widget][strip_widget_position]

Azimuth and elevation are the two parameters available to define the position of keyframes. Azimuth is define in a range of -180 to 180 degrees, and elevation in a range of -90 to 90 degrees.
You can use those buttons, the toolbar are also move the colored dot related to this channel for changing the position.

Actually distance is a static parameter set to 1.0 meter. 

### MixFocus controls

![strip widget][strip_widget_mixfocus]

Mix focus can be set by using radius, gain at center and gain at border.
Radius is simply the value of the circle radius representing the effect area. Gain at center/border are defined by a gain in decibel in a range of -60 to 60.

## Pie menu

Edit and manipulate keyframes has been improved by the use of Pie menu also known as radial menu.

![pie menu overview][pie_menu_overview]

You can invoke this menu by maintaining right click on top of keyframes. This will automatically show you wich channel you selected in "channels" widget.
In few clicks and movements, you can easily :
   - go to next keyframe
   - go to previous keyframe
   - mute/unmute
   - solo
   
![pie menu alternative overview][pie_menu_alt_overview]

An alternative menu can be invoke if you use alt key with few options like :
   - consolidate/remove (create new or remove keyframe at current time)
   - lock/unlock keyframe (no position interpolation until the next keyframe)
   - hide/show channel
   - hide all except current channel
   
## Move/remove keyframes

Removing a lot of keyframes can be bone by using the edit menu.

![remove overview][keyframe_remove_overview]
![move overview][keyframe_move_overview]

Simply select options and click ok for move or remove keyframes.

## OSC control


## Read more

First project: [create an empty project and start spatialization][first_project] 
	
Automation: [explanation of Automation][automation_page] 

Strip widget: [explanation of strip widget][strip_widget_page] 
