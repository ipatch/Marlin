## ❗️ Warning

This is an incomplete fork of Marlin 2.0.x to work with a _Creality_ **CR-10S Pro** 3d printer.  Some componentes of the printer remain stock, while other have been upgraded or removed entirely.

## Preamble

Additional documentation can be found at the [Marlin Home Page](https://marlinfw.org/).
Please test this firmware and let us know if it misbehaves in any way. Volunteers are standing by!

- upgraded from stock touch screen to **12864 full graphics display**
- upgraded from stock logic board to **SKR v1.3** with TMC 2208 v3 stepper drivers in UART mode
- upgraded stock hot end to Mosquito hotend.
- upgraded stock build plate to a ~~Wham Bam~~ with a PEX top layer / coating, and spent several hours scraping existing Al build surfaces.
- upgraded extruder to **zesty nimble v1**
- installed a zsync mount for top of z axis rods using a GT2 belt along with two GT2 20 tooth pulleys.
- replaced stock build plate adjustment springs with nylon spacers

> this fork of marlin has been tweaked to accommodate the above listed upgrades

## Understanding Changes

I've tried my best to list the changes I've made to the **Configuration.h** and **Configuration_Adv.h** files with `todo ipatch,` or `todo ipatch, ia github src` single line C style comments ie. `//`

- **todo ipatch, ia github src** I'm using the `#define` statement described from the IA github Marlin fork linked below.
- **todo ipatch** is a setting I tweaked, more than likely from watching a YouTube video.

I've been modifying the source using VS Code on macOS, and have been building Marlin 2.0.x using the integrated Platform IO VS Code extension.

To build Marlin 2.0 you'll need [Arduino IDE 1.8.8 or newer](https://www.arduino.cc/en/main/software) or [PlatformIO](http://docs.platformio.org/en/latest/ide.html#platformio-ide). We've posted detailed instructions on [Building Marlin with Arduino](https://marlinfw.org/docs/basics/install_arduino.html) and [Building Marlin with PlatformIO for ReArm](https://marlinfw.org/docs/basics/install_rearm.html) (which applies well to other 32-bit boards).

This git repo tracks the upstream bugfix-branch of marlin 2.0 and I pull those changes into the same branch locally within this repo, then create a new branch from pulled in changes on my local fork of marlin then merge in my changes that I've applied to _configuration.h_ and _configuration_adv.h_ files, and try to squash all merge conflicts in the process.

### alt git workflow

If shit hits the fan, (and it will) checkout upstream changes into local bugfix branch, then create a new branch from upstream bugfix branch and merge each file independently until the build succeeds.

- Marlin/Configuration.h
- Marlin/Configuration_adv.h
- Marlin/_Bootscreen.h
- Marlin/_Statusscreen.h
- README.md _this file, **not** its upstream counterpart_
- platofrmio.ini

To merge in each of the modified files one by one using git from a CLI.

```shell
cd "project root"
git checkout -b fresh-new-bugfix-2.0-branch-from-upstream
git checkout --patch previous-custom-marlin-branch Marlin/Configuration.h
```

## Future Upgrades

- ~~install Zesty Nimble~~
- ~~install wambam build plate~~

## Inspiration

This fork has added settings from watching various YouTube videos _too many to link to every single video_.  And has also been heavily inspired by the [InsanityAutomation fork](https://github.com/InsanityAutomation/Marlin) of Marlin, and more specifically ~~the [CrealityDwin_2.0](https://github.com/InsanityAutomation/Marlin/tree/CrealityDwin_2.0) branch from the InsanityAutomation fork of Marlin~~.

## TODOs

- [ ] setup a pin in the skr boards configuration pins file to map a pin for the filament run out sensor.
- [ ] convert printer to a smooth rail setup a la prusa style printer.
- [ ] display **layer #** of **tot num of layers** on 12864 display
- [ ] display **total time printing** and toggle between, **total time** & **remaining time**
- [ ] setup custom boot logo _personal logo_ for marlin boot process on 12864 display.
- [ ] see if it's possible to display the current speed of the current operation being performed.
- [ ] make _heater gun_ detachable from 858D unit using 7 or 8 pin GX aviation style connector(s)
