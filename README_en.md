English | [**한국어**](README.md)

# Neo Ergo Tri-mode — VIA Custom Firmware

## ⚠️ Warning

<span style="color:red">We take no responsibility for any problems. Please make sure you understand the risks before starting.</span>
<span style="color:red">Save your keymap first. Flashing new firmware overwrites all settings with the built-in default layout.</span>
<span style="color:red">It's a good idea to keep the stock firmware handy in case something goes wrong.</span>

Author: NARZ  
Latest version: **v2.9** (`NeoErgo_trimode_via_v2.9_NARZ.bin`)

## ✨ Features

A few things the stock firmware can't do:

1. Advanced keycodes like MT and LT work in wireless mode too.

2. **LED sleep behaves differently by connection type.**
   - Wired: LEDs turn off after **10 minutes** with no key input. The MCU stays awake, so USB keeps working.
   - Wireless: LEDs go to sleep after **2 minutes** to save battery.

3. **LEDs fade out and in over 3 seconds.** No abrupt on/off — much easier on the eyes.

## What this fixes

The stock Neo Ergo tri-mode firmware does support VIA, but some advanced keycodes don't work properly in wireless mode. I made VIA support more complete and reworked the LED sleep and fading behaviour.

## Source

This firmware is based on QMK (GPL-2.0-or-later). The modified source is available at [NEO-ERGO-VIA-SOURCE](https://github.com/narznarz/NEO-ERGO-VIA-SOURCE).

## Version history

### v2.0
- Wireless LED and core power saving — 2-minute timer, 20-minute wireless module timer
- 10-minute idle LED timeout on wired

## Keys supported in wireless mode

- MT / LT (Mod-Tap / Layer-Tap) and more
- LSG / MEH and other combos

## Flashing

1. Run [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases) as administrator
2. Battery switch OFF
3. Hold the ESC key to the left of the number 1 key (matrix position 0,0) while plugging in USB-C → DFU mode. If a red driver message appears, click the WinUSB driver install button
4. Select `NeoErgo_trimode_via_v2.9_NARZ.bin` → Flash
5. Click EXIT DFU

## Changelog

## v2.9

LED behaviour is optimised. Depending on the connection mode, a single LED in the top area shows the status by colour, and the RGB toggle turns the top, left and inner LEDs on and off.
There are eight combinations in total, so it takes a bit of fiddling — but pressing the RGB toggle eventually gets you exactly the lighting you want.
Even at the lowest RGB speed the animation used to keep moving; now it stops properly. In that state you can still adjust saturation, brightness and colour (in specific RGB modes).

On power-up and on wake from sleep, brightness ramps up gradually for a more refined feel. Key presses are still handled immediately, though.

The wireless sleep algorithm has been optimised too.
