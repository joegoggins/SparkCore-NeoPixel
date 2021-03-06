SparkCore-NeoPixel
==================

A library for manipulating NeoPixel RGB LEDs for the Spark Core.
Implementation based on Adafruit's NeoPixel Library.
Library currently supports WS2812, WS2812B GRB 800kHz style pixels, strips and sticks!
WS2811 RGB 400kHz style pixels, strips and sticks!

Also supports Radio Shack Tri-Color LED Strip with TM1803 controller 400kHz bitstream.

Components Required
---
- A Neopixel digital RGB LED (get at [adafruit.com](adafruit.com))
- or a Radio Shack Tri-Color LED Strip (get at [radioshack.com](radioshack.com))
- A Spark Shield Shield or breakout board to supply neopixel's with 5V (see store at [spark.io](spark.io))

Example Usage
---

See this [flashable, rainbow example](firmware/examples/a-rainbow.cpp) for details, or, in a nutshell:

```cpp
Adafruit_NeoPixel strip = Adafruit_NeoPixel(PIXEL_COUNT, PIXEL_PIN, PIXEL_TYPE);
void setup() {
  strip.begin();
  strip.show();
}
void loop() {
  // change your pixel colors and call strip.show() again
}
```

Nuances
---

- Make sure get the # of pixels, pin number, type of pixels correct

- NeoPixels require 5V level inputs and the Spark Core only has 3.3V level outputs. Level shifting is
necessary, the Spark Shield Shield has the [TXB0108PWR](http://www.digikey.com/product-search/en?pv7=2&k=TXB0108PWR) 3.3V to 5V level shifter built in, alternatively you can wire up your own with a [SN74HCT245N](http://www.digikey.com/product-detail/en/SN74HCT245N/296-1612-5-ND/277258), or [SN74HCT125N](http://www.digikey.com/product-detail/en/SN74HCT125N/296-8386-5-ND/376860).


Building locally
---

If you are building locally, place the files here:

```
..\core-firmware\inc\neopixel.h
..\core-firmware\src\application.cpp (renamed from extra-examples.cpp)
..\core-firmware\src\neopixel.cpp
..\core-firmware\src\build.mk (optional, if you have your own make file going, just add the neopixel.cpp to it)
```

Useful Links
---

- NeoPixel Guide: https://learn.adafruit.com/adafruit-neopixel-uberguide
- Octal Level Translator Breakout Board: https://www.adafruit.com/products/395
- Quad Level Shifter IC: https://www.adafruit.com/product/1787
