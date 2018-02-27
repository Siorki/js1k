My entry "The sound of chaos" to js1k 2018

Upload any image and listen to how it sounds. Procedural chaos provided as example.

------

Best used with images 192 pixels in height, larger ones will be truncated.
Now you can use GIMP as a sound editor :)

Technical details : 
* two pixels equal one halftone => 1 octave every 24 pixels, from C1 (bottom) to a quartertone above B8 (top)
* red channel for sawtooth wave
* green channel for sine wave
* blue channel for square wave
* volume is always amplified to maximum range without saturation (thus a linear increase in brightness will have no audible effect)
 
A good subwoofer is recommended to hear the first two octaves, typical laptop speakers will not cut it.
 
Inspired by Photosounder and SonicPhoto.