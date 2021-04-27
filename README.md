# Neopixel Driver Build Notes 2/2/20

This project is in partnership with [Bantam Tools](https://www.bantamtools.com)

**Design Notes:**

This driver board is intended to facilitate large Neopixel arrays through split power/ground lines for power injection.  The board is split into two sides as power and ground planes.  A 1000uF capacitor sits between them to prevent damage to the Neopixels from a rush of current when first powering them on.  A 470Ω resistor lies in series with the data line so as to prevent damage to the first pixel due to spikes in the signal.

The power and ground planes feed into 3 terminal blocks, respectively, allowing for up to 6 lines of power injection.  Additionally, there are 4 mounting holes for M3 screws. The graphic below shows a potential use case.

![](https://github.com/jps723/neopixelDriver/blob/master/images/diagram.png)

*Note: This is intended for use with 5v microcontrollers.  Controllers outputting 3.3v or similar (i.e. raspberry pi/teensy) may require level shifting on the data line.

# Build Process
**Bit:** 1/32”
**Mill Time:** ~5mins

It’s easiest to solder in this order:
```
1. Resistor
2. Capacitor
3. Screw Terminals
```

**Test**

Run Strandtest from the Adafruit Neopixel library examples.  Pin6 is the default data pin.  Test with a voltmeter at each of the screw terminals.  
