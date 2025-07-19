**[Through the nebula](https://js1024.fun/demos/2025/23/readme)** is my entry to the 2025 edition of js1024.fun
Theme was *Creepy*


The demo was inspired by
- NASA picture of [NH95](https://en.wikipedia.org/wiki/Main_sequence#/media/File:LH_95.jpg) in Large Magellanic Cloud

- [Andrioli Galaxy tour](https://js1k.com/2019-x/demo/4238) by Denys Potapov, 4th at js1k 2019

- [Star Trek](https://codepen.io/atzedent/pen/NPKeGYJ) by Matthias Hurrle


The latter two used WebGL shaders for their effects, and I endeavored to reach a similar result using only 2d. The trick to achieve this required a creative (ab)use of the `lighter` composite operation.

Two offscren 2d canvases are used for that purpose, initialized once then used read-only.
The first one contains a single cloud (radial gradient, RGB #140E08 inside, translucent black outside). Copying with `drawImage` is faster than recreating a gradient (well, 3000 of them) each frame
The second one is populated with random stars on the top half, and clouds on the bottom half. Colors range from orange to white to ice blue, from the [main sequence](https://en.wikipedia.org/wiki/Main_sequence).

On the main screen are drawn, in the following order :
- clouds from the [accretion disk](https://en.wikipedia.org/wiki/Accretion_disk) of the black hole. Being more densely packed at the center of the screen, the `lighter` composition ensures they are of a lighter color, reaching white at the center
- black center (actually the top half of a disk) of the black hole, drawn with `source-over` composition 
- 4 layers of stars, with an increasing zoom level to mimic parallax, taken from the offscreen canvas
- 18 layers of clouds, with the same setup. Multiple clouds overlaid are rendered with a lighter color, giving them a fuzzy look
- the two spaceships, each one defined as a thin rectangle in a radial gradient


As usual, the demo comes in three flavors :
 - original code with meaningful functions and variable names
 - hand minified code, one-letter variables, functions collapsed
 - Regpack'ed code, 1024 bytes or less
