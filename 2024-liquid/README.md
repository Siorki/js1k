**[Fireworks over water](https://js1024.fun/demos/2024/8/readme)** is my entry to the 2024 edition of js1024.fun
Theme was *Liquid*

Spoiler : the demo uses a second canvas onscreen.

Text is initially written as black on black on the canvas, then discretized into triangles (one for each pixel).

The mirror effect uses a completely different technique than the one I used in 2022 for Hudson River.
Here, raw pixel data obtained through `getImageData` is accessed, at coordinates altered with two sinusoids to simulate the wave effect, and stored into the pixel buffer of the second canvas.

As usual, the demo comes in three flavors :
 - original code with meaningful functions and variable names
 - hand minified code, one-letter variables, functions collapsed
 - Regpack'ed code, 1024 bytes or less
