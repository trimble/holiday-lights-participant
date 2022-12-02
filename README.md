# SEP Makes Holiday Light Display Challenge

This is the technical companion for the SEP Makes Holiday Light Display Challenge.

# Technical Details

The system is built using an ESP32 and some WS2812 RGB light strips.

Specifically...

## Hardware Setup

* ESP32 - AdaFruit Huzzah 32 Feather (https://learn.adafruit.com/adafruit-huzzah32-esp32-feather)
* LED Strip - (https://a.co/d/iEG4w1d)
* Jumper wires - (https://a.co/d/8bPsRG8)
* 18" Christmas tree

## Software Setup

* Arduino IDE - https://www.arduino.cc/en/software
* ESP32 board
  * In _Preferences_, add this as a board manager url: `https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json`
  * In _Tools > Board Manager_ search for ESP32, install.
  * The board we're using is the `Adafruit ESP32 Feather`.
* Libraries
  * `FastLED`
  * `Adafruit_GFX_Library`
  * `FrameBuffer_GFX`
  * `FastLED_NeoMatrix`

# Creating Your Light Display

It's as easy as writing a single function!

Here's what you need to do:
1. Write a parameterless function with return type `void`.
1. Modify the contents of 3 arrays: `leds1`, `leds2`, `leds3`
    * Each array is `NUM_LEDS` long. `NUM_LEDS` is 300.
    * Each array element is a [CRGB structure](https://fastled.io/docs/3.1/struct_c_r_g_b.html)...a hex color code in the form 0xRRGGBB
1. Prefix your function and all helper methods with your initials (e.g. `JCF`).
1. Think of a title for your creation. Ideally something that is 16 characters or less.
1. Test it on the rig by Jon's desk.
1. Please! No `delay`s or crashing.

Note:
* Your function will get called repeatedly in a loop.
* The driver loop will take care of sending the data to the LED strips.
* Take a look at the FastLED docs: https://fastled.io/docs/3.1/

## Some More Details

There are a couple pieces of state that do change during the program. You are encouraged to take advantage of them to make your display more dynamic:

* `gLoopCounter` - Starting at 0, increments each time through the loop.
* `gHue` - increments roughly every 20ms

## Need Help or Inspiration?

The repo comes with a few samples to get you started:

* `straightYesChaser`
* `rainbow`
* `confetti`
* `sinelon`
