# sun-now
Where is the Sun now?
## Typical output
    [11:21]~$ sun
     alt:  53
      az: 134
## Compile
Edit the `sun.c` file to provide your latitude and East longitude (lines 11 and 12) and save then
     cc sun.c -lm -o sun
## Installation
Just copy the `sun` executable to somewhere on your path or run from the directory where you compiled it with the command `./sun`.
## Background
The program is basically a step by step implementation of the calculation that you will find on page C24 of a copy of the Astronomical Almanac dating from sometime in the last couple of decades. No loops and only one function. I've been very wasteful of multiplications (repeated conversions of arguments to and from radians for instance) and calls to sine and cosine.

The accuracy of the C24 method is around 0.1 degrees 'most of the time' with some peaks in the error curve of the kind that you begin to recognise from these truncated expansions of trigonometric terms, so good to roughly half the diameter of the Sun's disk. I just need a rough idea where the Sun is when it is behind the clouds, so the output is rounded to the nearest whole degree. Refraction effects come into play as the Sun is setting, say altitudes below 3 degrees.
