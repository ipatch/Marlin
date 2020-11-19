## Working with prusa slicer

To calculate the extrusion multiplyer for a particular filament

**EM** _Extrusion Multiplyer_ = 0.45 _expected layer width_ / actual layer width

---

_Example_

EM 0.8823 = 0.45 / 0.51

## Working with filament

PETG can be dried using a standard kitchen oven by setting the temp to 120ºF and placing it on a standard baking sheet, then leaving the filament in the oven for ~ 30 minutes and checking up on it in 30 minute increments.

## Working with temperatures

- converting **Celsius** to **Fahrenheit** formulas, and versa
  - Fº = Cº * 1.8 + 32
  - Cº = (Fº - 32) * 5/9

- approximate ~ calculations
  - Fº = C * 2 + 30

## Connecting to a BigTreeTech SKR v1.3

On macOS the physical USB port on the SKR v1.3 shows up as `/dev/tty.usbmodem14111` which can be used to interface with the device using _Pronterface_ / _PrintRun_.

The same device can be passed through to VirtualBox by setting up a USB filter

> ❗️ The VM must be shut down first and the filter must be setup in the VM settings in order for the VM to pickup on the device because macOS doesn't provide a facility for keeping the device plugged in and allowing it to pass through to a VM.

When using a USB port through a VM _Windows 10_ verify the VM has _captured_ the USB device, ie. **Marlinfw USB device**, and that the appropriate com port is selected in _whatever_ app is interfacing the pass through USB device.

## Solved ✅ Octoprint Reconnection Issues

The settings provided in the below image solved my [reconnection](https://youtu.be/ZBZJcJXvm4w) issues using Octoprint with my Raspberry Pi connected to my SKR v1.3 logic board, [youtube explanation](https://youtu.be/ZBZJcJXvm4w) The below image of the BTT TFT35v3 show where I connected my Raspberry Pi.

<div align="center">

<img src="https://raw.githubusercontent.com/ipatch/Marlin/ibuild-marlin2-bugfix/media/octoprint-recolla.png" alt="octoprint-reconnection-settings">

<img src="https://raw.githubusercontent.com/ipatch/Marlin/ibuild-marlin2-bugfix/media/btt-tft35v3.png" alt="octoprint-connection-issues">

</div>

## Understanding {x,y,z} min / max voltages on a skr v1.3

in the accompanying picture within this directory the {x,y,z} min/max pins are outlined with rounded purple rectangles. when hooking up my multimeter to the X- _x min_ i get ~ 4.5 to 5VDC when the probes are connected to the +5V and GND connection within the 3 pins designated for the _x min_ port.

However, when i connect the _GND_ and _pin 1.29_ of the _x min_ to my multimeter I get ~ 3.3VDC coming from the _GND_ and the _1.29_ pin of the _x min_ port 

❓ Why would the port report two different voltages?

## btt skr v1.3 pin diagram

<div align="center">

<img src="https://raw.githubusercontent.com/ipatch/Marlin/ibuild-marlin2-bugfix/media/skr-v13-endstop-voltages.png" />

</div>
