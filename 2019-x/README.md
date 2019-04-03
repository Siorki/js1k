js1k 2019 allowed multiple entries, I managed to get two ready in time. There was one more, this is left unfinished and kept for a later date.

Dark fluorescence

The soundtrack for this demo is a cover of Blood Money ingame music by Ray Norrish.
The 1k limit meant I had to cut out the first pattern, along with the drum and bass lines, leaving only the melody.
The lead instrument is an electric guitar simulated with [Karplus-Strong](https://en.wikipedia.org/wiki/Karplus%E2%80%93Strong_string_synthesis) algorithm.

The animation is synced with the music every half pattern (about 4s). It features shadebobs drawing a curve defined by the Hopalong formula :

```javascript
X = y-sign(x)*sqrt|ux+v|  // sign is -1 for negative values and 1 for positive values
Y = -x

// x and y are reset to (4,.265) at the beginning of every drawing.
// u and v change for each pattern
```


Chrome users : your browser now disables sound autostart by default. The animation being synced with the music, it will not play either.
To see the demo, change "Autoplay Policy" to allow music playback without user gesture at chrome://flags/#autoplay-policy 



---

Maximum overcast

This one is a remake of my 2013 entry [Comanche](https://js1k.com/2013-spring/demo/1450), featuring more fancy stuff than the original.
(including clouds, I initially wanted to name it Comanche : maximum overcast to echo the original maximum overkill but hit the 20-char name limit)

Rendering is still done in voxel blocks, front to back, however the new version writes to a data buffer, instead of drawing canvas primitives, which is way faster.
The net increase in speed allows for a gain in resolution (4 pixels instead of 8), along with a more detailed landscape. The grid is now 512x512 instead of 256x256 for the same area, reducing the blocky aspect.

Finally, the formerly clear skies are now home to a cloud layer, slowly drifting with the wind. The sun is still present though, but sometimes hidden behind the clouds.




