---
layout: page
title: motion_capture
permalink: /static/kavi/motion_capture/motion_capture/
---

[**<-back**](/static/kavi/motion_capture)  

# Dataset capturing set-up

## Equipment

| **Quantity** 	| **Name**                    	| **Image** 	|
|:-------------	|:----------------------------	|:----------: 	|
| 1            	| MotionAnalysis L-frame      	||
| 1            	| MotionAnalysis 20mm CalWand 	||
| 1            	| Clapper board               	||
| 1            	| Radio mic set               	||
| 1            	| Sigma 50mm Art Lens         	||
| 1            	| Sigma DSLR 85mm Lens        	||
| 1            	| Sigma 50-100mm Art Lens     	|<img src="img/zoomlens.jpg" width="200" height="150"/>|
| 1            	| Panasonic Varicam LT        	|<img src="img/ltcam.jpg" width="200" height="150"/>|
| 1            	| 50Hz signal generator       	|<img src="img/signalgen.jpg" width="200" height="150"/>|
| 3            	| KinoFlow BAL-427            	|<img src="img/kinoflow.jpg" width="200" height="150"/>|
| 9            	| Raptor-E                    	|<img src="img/raptor.jpg" width="150" height="200"/>|
| 2            	| Kestrel 2200                	|<img src="img/kestrel.jpg" width="150" height="200"/>|
| 1            	| Face marker set             	|<img src="img/markers.jpg" width="150" height="200"/>|

## Physical setup

Final setup:

<img src="img/finalsetup.jpg" width="800" height="600"/>>

* Remember to place the network switches close together and use the shortest wire possible to link them.
* Connect genlock signal generator to one of the Kestrels.
* Aim all mocap cameras towards face of the subject
* Attach large (45mm) markers to jaws and hinge of clapper board

## Live capture
### Video camera settings
* Remove HUD information from output: `Menu > Output setting > SDI Out > Clear view`
* Send test signal: `Menu > Output setting > Test SIG`
* 50Hz and 25fps, RAW 4k/10bit
* 3440K colour temp
* ISO 800
* Shutter speed 1/100

### Cortex settings
* Change panel layout: `Layout > ...`
* Change Data view: `Data View > ...`
* Change working folder: `Quick Files > Set as working dir`
* Change marker size: `Tools > Settings > Tracking`
* Set camera with the genlock signal as master:
	1. Right-click 3D display panel
	2. `Additional settings > Cameras`
		* Master sync: Internal
		* Slave sync: Ethernet
		* IP addr: 10.1.1.190 
* Define a 1m^3 capture volume:
	* `Tools > Settings > Calibration > Capture volume`
		* Xmin: -250
		* Xmax: 750
		* Ymin: 0
		* Ymax: 1000
		* Zmin: -250
		* Zmax: 750
3D view navigation:
	* Translate: L-Alt + MMB
	* Zoom in: L-Alt + Scroll down
	* Zoom out: L-Alt + Scroll up
	* Rotate: L-Alt + LMB + mouse_direction

		
### Mocap calibration
1. Check if capture volume is empty, live feed should show 0 markers. If not, adjust threshold and brightness sliders until it is. Might also have to mask certain problematic areas of the screen:
	1. Right click on camera's view
	2. `Auto mask selected camera`
2. Place L-frame level in the capture volume so that all cameras can see it
3. Calibrate L-frame:
	1. `Calibrate > Initial calibration`
	2. Rename CalFrame if needed
	3. press Next
4. Remove L-frame from volume
5. Calibrate wand:
	1. Rename CalWand if needed
	2. press next
	3. Move into volume with 20mm wand and wave it around until all camera screen regions are green
	4. `Stop capturing wand data`
	5. Press Next


## Cortex post processing

Creating a template:

1. Take a short capture of the subject \~5s
2. Pause live camera feed
3. `Load last capture`
4. `New > Marker Object`
5. Name all markers
6. `Quick ID`
7. Create links
8. `Rectify`
9. `Delete Unnamed`
10. `Create Template`


