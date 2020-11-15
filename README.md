# tb.music_box
DIY Raspberry Pi Music Box

## Introduction and Goals

### Main requirements

* >=3W speaker power

## Drivers and Constraints

* Easy to assemble
* Very robust -> Mechanics and software
* Children friendly
* Good sound quality
* Portability/Low power consumption

* Sound quality over Portability/Power consumption?
* Costs?

## System Context

* FM Radio?
** Preferably not because it needs an "audio out" selection or digitalization
* DAB Radio?
** E.g. MonkeyBoard (with DAB) too big
* Headphone Out

## Decisions

### Laufzeit + Batterie

### Amplifier

* Mono/Stereo -> Stereo (siehe Boomboxes und Anwendung als "Fernseher")
* For portable usage (low current consumption)

* No separate power supply!
* With development resources and proven-in-use
* Low PCB count

* Soundcard or amplifier? -> Preferably soundcard for I2S usage (instead of Raspberry Pi PWM)

* Adafruit I2S 3W Mono Amp MAX98357A: https://www.adafruit.com/product/3006, https://learn.adafruit.com/adafruit-max98357-i2s-class-d-mono-amp, https://learn.adafruit.com/adafruit-max98357-i2s-class-d-mono-amp/pinouts
** Mono and no headphone out

* DACBerry AMP   3W Stereo Amp: https://www.osaelectronics.com/product/dacberry-amp-for-raspberry-pi-zero/
** Sold out

* DACBerry AMP+ 10W Stereo Amp: https://www.osaelectronics.com/product/dacberry-amp-plus/
** 10W too much, has headphone out, apart it fits perfect

* WM8960 Stereo Amp (1W Speaker + Headphone): https://www.waveshare.com/wm8960-audio-hat.htm, https://www.waveshare.com/w/upload/1/18/WM8960_v4.2.pdf, https://www.waveshare.com/w/upload/f/fa/WM8960_Audio_HAT_Schematic.pdf, https://www.waveshare.com/wiki/WM8960_Audio_HAT, https://www.reichelt.de/raspberry-pi-shield-hi-fi-stereo-sound-hat-wm8960-rpi-shd-stereo-p266063.html
** Only 1W

* HiFiBerry DAC2 Pro: https://www.hifiberry.com/shop/boards/hifiberry-dac2-pro/, https://www.hifiberry.com/docs/data-sheets/datasheet-dac2-pro/
* HifiBerry Miniamp: https://www.hifiberry.com/docs/data-sheets/datasheet-miniamp/
** HifiBerry only has digital or analog AMPs 

* Adafruit I2S Stereo Decoder, https://www.adafruit.com/product/3678, https://learn.adafruit.com/adafruit-i2s-stereo-decoder-uda1334a
** Only line output, but apparently headphones work with distortions, but no jack detect switch

* Adafruit Mono Amp: https://www.adafruit.com/product/2130
** Only 2.5W

* Stereo 3.7W Class D Audio Amplifier - MAX98306 + Klinkenanschluss: https://www.adafruit.com/product/987, https://learn.adafruit.com/stereo-3-7w-class-d-audio-amplifier, https://learn.adafruit.com/stereo-3-7w-class-d-audio-amplifier/inputs-and-outputs, https://learn.adafruit.com/stereo-3-7w-class-d-audio-amplifier/build-a-portable-sound-system, https://cdn-shop.adafruit.com/datasheets/MAX98306schem.png
* Cheapest solution: https://forums.adafruit.com/viewtopic.php?f=19&t=144892, https://www.adafruit.com/product/1700, https://forums.adafruit.com/download/file.php?id=63172&sid=0f47a811efd81ec87bd2b66c538b6e77, https://learn.adafruit.com/adafruit-tpa2016-2-8w-agc-stereo-audio-amplifier?view=all, https://www.adafruit.com/product/1699
** Uses Raspberry Pi (poor?) PWM Audio Out, needs some wiring, but receives good reviews

### Speaker

* Speaker 4Ohm 3 Watt: https://www.adafruit.com/product/1314

### Battery

* Lithium Ion Polymer Battery - 3.7v 2500mAh ???|https://www.adafruit.com/product/328

### Buttons

* Rugged Metal On/Off Switch with Green LED: https://www.adafruit.com/product/482

## Solution Strategy

## Building blocks

### Main parts list

|Part|Link|Cost|Amount|
|---|---|---|---|
|Raspberry Pi Model 3 A+|https://www.adafruit.com/product/4027|25$|1|
|PiTFT 3.5"|https://www.adafruit.com/product/2097|44.95$|1|
|PowerBoost 1000 Charger|https://www.adafruit.com/product/2465|19.95$|1|
|Amp|?|?|
|Speaker|?|?|
|Battery|?|?|
|Buttons|?|?|
|Case|?|?|

### Auxiliary parts list

|Part|Link|Cost|Amount|
|---|---|---|---|
|Assembled Pi T-Cobbler Plus|https://www.adafruit.com/product/2028|7.95$|1|
|Pimoroni Mini Black HAT Hack3r|https://www.adafruit.com/product/3182|14.95|?|
|Adafruit Perma-Proto HAT for Pi Mini Kit|https://www.adafruit.com/product/2310|4.95|2|
|Stacking Header|https://www.adafruit.com/product/1979|2.95$|?|
|GPIO Header|https://www.adafruit.com/product/2222|1.50$|?|
|GPIO Ribbon Cable|https://www.adafruit.com/product/1988|2.95$|?|
|Raspberry Pi Camera|https://www.adafruit.com/product/3099|29.95$|?|
|Adafruit Breadboard|https://www.adafruit.com/product/4354|7.95$|1|
|Tweezer|https://www.adafruit.com/product/422|3.95$|1|
|Breadboarding/Jumping Wires|https://www.adafruit.com/product/153|4.95$|1|
|Abstandshalter (12mm) und Schrauben M2.5||||
|Einbaumutter M2.5||||

## Questions

## Knowledge

### Impedances

|Input/Output Type|Typical Impedance Range|Typical Voltage Range (Nominal)|
|---|---|---|
|Mic Level Output|50 \Omega to 600 \Omega|-60 dBV (1 mVRMS) to -40 dBV (10 mVRMS)|
|Mic Level Input|1.5 to 15 k\Omega|-60 dBV (1 mVRMS) to -40 dBV (10 mVRMS)|
|Instrument (Hi-Z) Level Output|10 k\Omega to 100 k\Omega|-20 dBu (77.5 mVRMS)|
|Instrument (Hi-Z) Level Input|47 k\Omega to over 10 M\Omega|-20 dBu (77.5 mVRMS)|
|Line Level (Professional) Output|75 to 600 \Omega|+4 dBu (1.228 VRMS)|
|Line Level (Professional) Input|10 k\Omega to 50 k\Omega|+4 dBu (1.228 VRMS)|
|Line Level (Consumer) Output|75 to 600 \Omega|-10 dBV (316 mVRMS)|
|Line Level (Consumer) Input|10 k\Omega to 50 k\Omega|-10 dBV (316 mVRMS)|
|Speaker Level Output|<100 m\Omega|20 dBV to 40 dBV (10 VRMS to 100 VRMS)|
|Speaker Level Input|4 \Omega to 16 \Omega|20 dBV to 40 dBV (10 VRMS to 100 VRMS)|
|Aux Output|75\Omega to 150 \Omega|-10 dBV (0.300 VRMS)|
|Aux Input|>10 k\Omega|-10 dBV (0.300 VRMS)|
|Headphone Jack Output|0.1 \Omega to <24 \Omega|N/A|
|Headphone Amplifier Output|0.5 \Omega to >120 \Omega|N/A|
|Headphone Input|8 \Omega to 600 \Omega|N/A|
|Raspberry Pi (PWM) Audio Jack Output|See Line-Out and note below|See Line-Out|

Note: https://hackaday.com/2018/07/13/behind-the-pin-how-the-raspberry-pi-gets-its-audio/

## References

* https://learn.adafruit.com/touch-pi-portable-raspberry-pi
* https://learn.adafruit.com/adafruit-pitft-3-dot-5-touch-screen-for-raspberry-pi
* https://learn.adafruit.com/raspberry-pi-radio-player-with-touchscreen
* https://www.reichelt.de/magazin/how-to/kodi-internetradio/
* https://learn.adafruit.com/raspberry-pi-as-a-media-center
* https://www.circuitbasics.com/setup-lcd-touchscreen-raspberry-pi/
* https://www.reddit.com/r/raspberry_pi/comments/3belpg/adafruit_pitft_kodi/
* https://www.opendisplaycase.de/opendisplaycase.html
* https://www.opendisplaycase.de/tutorials/raspberry-pi-raspian-tft-displays.html
* https://www.opendisplaycase.de/opendisplaycase/up-board-kodi-mediaplayer-box.html
* https://en.wikipedia.org/wiki/Line_level
* Can You Use The Headphone Jack with the MAX98306 amp?: https://forums.adafruit.com/viewtopic.php?f=19&t=144892
* http://www.sengpielaudio.com/Rechner-EingangsAusgangsWiderstand.htm
* https://www.pcwelt.de/ratgeber/Digitalradio-mit-DAB-9733609.html