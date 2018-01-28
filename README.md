# Forked revision from 200 of http://bazaar.launchpad.net/~toykeeper/flashlight-firmware

This is forked out from [ToyKeeper's repository](http://bazaar.launchpad.net/~toykeeper/flashlight-firmware/trunk/files/200/Tom_E/narsil) because I wanted to add settings for [Lexel's board](http://budgetlightforum.com/node/54838) which I've installed in (Sofirn C8F host)[https://www.aliexpress.com/item/Sofirn-New-C8F-triple-reflector-host-16-5-17mm-for-driver-nice-design-side-switch-with/32847095613.html].

(Album link)[https://imgur.com/a/Fibgy].

# Changes:

- compilable under latest gcc under ArchLinux
- pasted Channels.h into NarsilM.c
- adjusted voltage and temperature offsets for used board
- changed order of biking strobe
- configured to use 3 channels board
- lowered momentary mode
- when light is locked out, moonlight mode works in momentary mode

# Uploading

Test connection:

    avrdude -c usbasp -p t85

Compile:

    cd narsil/NarsilMulti/Release
    make all

Upload hex file:

    avrdude -p attiny85 -c usbasp -u -Uflash:w:NarsilM.hex
