**[Hudson river][https://js1024.fun/demos/2022/32/readme]** is my entry to the 2022 edition of js1024.fun
Theme was *Mirror*

Building height and lit windows are random. So are mountains height in the background.

No WebGL, all 3D is done by hand (and the CPU). The perspective is chosen so that the drawing order is always correct.

Mirror effect on the river is achieved by copying vertical stripes using `drawImage` with a scale of (1, -1) and applying a semi-transparent color on top.

As usual, the demo comes in three flavors :
 - original code with meaningful functions and variable names
 - hand minified code, one-letter variables, functions collapsed
 - Regpack'ed code, 1024 bytes or less
