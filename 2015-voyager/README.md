My entry "Voyager" to js1k 2015

A space probe warp jumps from star system to star system, in a quest for a planet that could harbor life.

Contest results currently pending.

------

Both planet and sun are drawn in a cache first, then copied to the main canvas with the appropriate scaling, hence keeping a constant framerate. 
Sun and lens flare are draw using the "lighter" composite operation. The sun is drawn using 12 superimposed copies of the same gradient.

The planet generation algorithm comes from my 2013 entry "Comanche", altered to keep the seed in the interval [0,256[ so it can be reused for other purposes (star size, planet colors).
