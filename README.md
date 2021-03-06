Light Controller Knob 
=============================================

Code adapted from https://github.com/jonwaterschoot/Neopixel-day-night
Control RGB light bulbs using a rotary dial with Neopixel ring.

#Description
Physical controller for RGB home lighting aka MiLight, Lifx, Hue etc...  A thermostat-like knob will display different colors on a Neopixel ring depending on position of potentiometer. When desired color is selected a pushbutton communicates to a home controller via MQTT and the corresponding color change will be reflected in home light bulbs.

Original Documentation as follows will be edited as project progresses.

##The colors
* The colors are manually listed by mixing the main colors and noting down those values
* Colors are defined 1 to 60 and then backwards again. (hence the 'library' only consists of 60 colors)

##Setup
###Software
To run this code you will also need to install the Adafruit Neopixel Library:
https://github.com/adafruit/Adafruit_NeoPixel

In the Arduino code the global brightness is defined by:
```
leds.setBrightness(32); // Set global brightness for the whole strip 0-255
```
In other words: pump it up to 255 if you want full power. When breadboarding/prototyping I found it easier to see the colors when they're less bright. In an actual setup, or when diffused you might want to crank them up again.

####To Do:
I was thinking that dimming the outer LEDs of the 11-pixel array would provide an even smoother transition. But so far that hasn't worked yet. And in prototyping for our work, it's not clear yet whether it would make any real difference.

###Hardware
The hardware setup can be seen on the breadboard image made with Fritzing.
Remember to adjust the Pin you connect the data input to and number of pixels you have in your setup in the .ino file. 

Also, as can be read in the tutorials on the strip (see links below), take care of using the right power for your project. And protect the setup by using a capacitor. Possibly the 5V and the Amps supplied by the USB port might be sufficient because this code only lights up 11 pixels. But powering the full 120 pixels is probably a no go.

![Alt text](https://raw.githubusercontent.com/jonwaterschoot/Neopixel-day-night/master/hardwaresetup_breadboardview.png "breadboard view hardware")

------------------------------

##Sources and documentation
This code is the result of studying the Adafruit and Sparkfun guides on using WS2812 LEDs.
Adafruit Neopixel Überguide : https://learn.adafruit.com/adafruit-neopixel-uberguide/
Sparkfun: https://learn.sparkfun.com/tutorials/ws2812-breakout-hookup-guide/all

I also got great help by the user Grumpy_Mike (Mike Cook) on the Arduino forum who has spent a great deal of time on rewriting and simplifying my code:
http://forum.arduino.cc/index.php?topic=301375.0
He has some valuable tutorials and info about Arduino and electronics on his website http://www.thebox.myzen.co.uk/ 

Source of this text: https://github.com/jonwaterschoot/Neopixel-day-night
