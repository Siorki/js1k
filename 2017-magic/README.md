My entry "Watercolor artist" to js1k 2017

The artist is busy painting a lavender field, but give him any other model (upload an image file) and he'll immediately start working on it.

------

The demo is a animation of a lavender field being painted (see proceduralLavenderField.html for the source image).
At any time, you can upload another image file and the painting will restart from scratch, filling the white canvas until the image shows up.

The algorithm is to choose a point with maximum saturation (S in HLS color model) among a random subset and start a brush stroke from there. The brush moves 1 pixel up or down, depending where the applied color better matches the source image. It stops when the resulting pixels would be darker than the original, then another stroke begins.
Strokes alternate between left and right directions, and colors are multiplied, simulating translucency.
After 20 seconds, a bit of luminosity is added to the stroke selection, in order to fill dark areas which were previously ignored.

A tweak lets the algorithm work in grayscale images as saturation is always zero, leading to the first point in the set being picked each time. The set begins one line down each time, looping when it reaches the bottom of the image.

Test images included the original [Lena](https://en.wikipedia.org/wiki/Lenna), lake, mandrill, along with the [Self-Portrait with Grey Felt Hat](https://en.wikipedia.org/wiki/Vincent_van_Gogh#/media/File:Vincent_van_Gogh_-_Self-portrait_with_grey_felt_hat_-_Google_Art_Project.jpg) by Vincent Van Gogh.
