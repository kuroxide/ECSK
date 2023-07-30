# ECSK
An Extra/Exceptionally/Extremely/Ehhhhhhh Cheap Steno Keyboard based on a Raspberry Pi Pico

## Rationale
The ECSK designed to be simple and cheap enough that one person could plausibly build it themselves using tools and services that are readily available to them.
- The case can be easily 3D printed, or ignored entirely if using PCB-mount switches.
- The controller (Raspberry Pi Pico) is cheap and easy to source. It is also simple to program provided you have a basic understanding of Python and can read instructions. (However, the controller also turns out to be a potential caveat.)
- Through-hole components are easier to solder.
- The PCB can be ordered from any of several fabrication services. It can also be home-made if you have the setup for it (although this is out of the scope of the project.)
- If really necessary, the PCB could theoretically be replaced with a piece of plastic with some holes in the right places (this is also outside the scope of the project)

## Caveats
- The aforementioned controller. N-key rollover (which is essentially essential for a stenography keyboard) is somewhat patchy on KMK firmware. It is, as far as I know, not officially implemented but still somehow works half the time.
- Ergonomics. The layout has the hands very close together which can be uncomfortable. A wrist rest is recommended for long periods of use. (You can freely edit the design though.)
- Keycaps. F10 profile keycaps are recommended, but they can be difficult to get a hold of. G20 is also recommended. XDA profile keycaps are easier to get, but are less ideal for stenography.
- Repairability. This only applies if you use the case. In order to swap out a switch with the case, every single switch has to be desoldered.
- Speaking of soldering, you need a soldering iron.

## Parts
With that out of the way, we can get to the parts list. \
- Raspberry Pi Pico ($15AUD).
- 24 MX-style switches (~$25AUD). Very light linears are recommended (remember, you will be pressing lots of keys at once.) Gateron clears are a goodd choice. Get PCB-mount switches if you can't make the case, or if you care about repairability.
- 24 diodes ($12-$30AUD). I used some very cheap 1N4002 diodes (200 for $12AUD). Basically any through-hole diodes with a DO-41 footprint or 7.62mm pin pitch will work.
- 24 keycaps ($20-$infinityAUD). This really just depends on how much you're willing to spend. I used some blank XDA profile caps which I got for $20AUD.
- The PCB. The price for this is difficult to pinpoint. I got mine produced by JLCPCB for about $40AUD shipped. Keep in mind most fabs have a minimum order quantity.
- The case. This is free if you have a) A 3D printer ready to go or b) A friend/school/acquaintance who will let you use their printer. Otherwise, you can order it to be made with some service. I suggest ditching the case entirely and just going with PCB-mount switches.

## Building the board
All components should be soldered to the top of the PCB (the face with the silkscreen markings.) \
Step 0. If you are using the case, print it out. Snap all the switches in place, LED slot facing the bottom edge of the PCB. The bottom is the long edge closest to the controller's footprint. \
Step 1. Solder in all the diodes. Bend the legs to a 7.62mm pitch, then put them through the holes in the PCB with the cathode (marked with a line) facing the bottom edge of the PCB. \
Step 2. Solder in the Pi Pico. Try to line up the USB port with the edge. One method is to use some pin headers to align it while you solder some of the pins, then remove the header and solder the rest. \
Step 3. Solder in the switches. This is pretty self-explanatory. If you are using the case, place the case upside-down and lower the PCB onto it with the bottom face facing outwards, aligning the switch pins. \
Step 4. Flash CircuitPython and KMK onto the Pi Pico. This can be done at anytime. If you are using the case, you can press the reset button through the small hole in the top. \
Step 5. Program the Pico (.uf2 file to be added to this repo soon™) \
Step 6. Check if it works. \
Step 7. Stenography time! \

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.
