# Solid State Tesla Coil V2.0 (2020)

## Overview 
This is my second attempt at building a solid-state Tesla Coil. My first attempt can be found [here](https://github.com/zakwerd/Musical-Solid-State-Tesla-Coil-2019-)

I will be updating this page as I go to keep you updated on my progress and to serve as a beneficial resource for myself. Unlike my repository outlining my first attempt, this repository will most likely not go into as much detail regarding how each component works, unless I find it beneficial to the structure of my build updates.

However, I hope this serves a comprehensive enough overview to give any non-engineers a general idea of how SSTCs function, while not being overly technical with explanations.

## Interrupter Circuit 

### Overview  
The interrupter is used to prevent the transistors on the inverter (in my case it's a half-bridge inverter) from overheating. The transistors of the inverter are being switched by the UCC drivers at the resonant frequency of the coil (around 250kHz). To prevent the transistors from overheating, the interrupter turns on the gate drivers for a much smaller period of time (e.g. 100Hz with a 10% duty cycle: 90% less on-time compared to if there wasn't an interrupter).

Essentially, the interrupter is just a circuit that outputs a square wave. Because of this, it's quite easy to make an interrupter from a 555 timer chip. I've adopted a popular strategy of utilizing two 555 timers; an astable 555 timer's output is fed into the monostable 555 timer. By using potentiometers on each of the 555 circuits, I can thus have a controllable frequency and pulse-width. This enables me to create a variety of spark outputs.

Eventually, I want to make this Tesla Coil a "Musical Tesla Coil." Doing this is actually quite simple: you make the output signals of the interrupter match the frequency of musical notes. This can be done with an Arduino connected to a MIDI input in which the MIDI serial is converted into a note frequency.

### Circuit Analysis

![Interrupter Circuit Photo](https://user-images.githubusercontent.com/59108656/94471951-dc644d00-017e-11eb-86b4-4a0f826d36bd.png)  
*Photo of my interrupter circuit*  

On the left side, there is the astable 555 timer circuit. Its output (pin 3) is fed into pin 2 on the monostable 555 timer circuit. The left potentiometer is controlling the frequency of the final output signal (blue wire that the bottom probe is hooked to), and the right potentiometer is controlling the width of the final output signal. The blue LED is connected to the final signal output, allowing for a visual representation of the signal being created. The red LED is connected from power to ground to serve as a visual notification that the circuit is getting power in the case in which the blue LED is broken or one some other component is broken.


### Video Update
[A full video update of my interrupter circuit can be found here](https://www.youtube.com/watch?v=m8oV7pfkEEA&t=31s&ab_channel=MajorityBonePodcast)


## Credits

