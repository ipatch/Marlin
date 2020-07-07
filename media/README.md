## Connecting to a BigTreeTech SKR v1.3

On macOS the physical USB port on the SKR v1.3 shows up as `/dev/tty.usbmodem14111` which can be used to interface with the device using _Pronterface_ / _PrintRun_.

The same device can be passed through to VirtualBox by setting up a USB filter

> ❗️ The VM must be shut down first and the filter must be setup in the VM settings in order for the VM to pickup on the device because macOS doesn't provide a facility for keeping the device plugged in and allowing it to pass through to a VM.

When using a USB port through a VM _Windows 10_ verify the VM has _captured_ the USB device, ie. **Marlinfw USB device**, and that the appropriate com port is selected in _whatever_ app is interfacing the pass through USB device.

## Solved ✅ Octoprint Reconnection Issues

The settings provided in the below image solved my [reconnection](https://youtu.be/ZBZJcJXvm4w) issues using Octoprint with my Raspberry Pi connected to my SKR v1.3 logic board, [youtube explanation](https://youtu.be/ZBZJcJXvm4w) The below image of the BTT TFT35v3 show where I connected my Raspberry Pi.

<div align="center">

<img src="https://github.com/ipatch/Marlin/blob/0c7ffadac2133803d6d26a851596f8235fd40e77/media/octoprint-recolla.png" alt="octoprint-reconnection-settings">

<img src="https://github.com/ipatch/Marlin/blob/0c7ffadac2133803d6d26a851596f8235fd40e77/media/btt-tft35v3.png" alt="octoprint-connection-issues">

</div>

## Understanding {x,y,z} min / max voltages on a skr v1.3

in the accompanying picture within this directory the {x,y,z} min/max pins are outlined with rounded purple rectangles. when hooking up my multimeter to the X- _x min_ i get ~ 4.5 to 5VDC when the probes are connected to the +5V and GND connection within the 3 pins designated for the _x min_ port.

However, when i connect the _GND_ and _pin 1.29_ of the _x min_ to my multimeter I get ~ 3.3VDC coming from the _GND_ and the _1.29_ pin of the _x min_ port 

❓ Why would the port report two different voltages?

## btt skr v1.3 pin diagram

<div align="center">

<img src="https://github.com/ipatch/Marlin/blob/e5f9a85a9c8b5ce65aac79301c97dbeb23aa5428/media/skr-v13-endstop-voltages.png" alt="skr13-pin-diagram" />

</div>
