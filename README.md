# qmk
My QMK layouts

- Redox v1;
- BFO-9000: 2x6x9 layout.

## Pre-requisite

```bash
brew install ideviceinstaller
brew install --HEAD libimobiledevice
brew unlink usbmuxd && brew link usbmuxd
brew install --HEAD usbmuxd
brew unlink usbmuxd
```

## Flash the keyboard

1. Disconnect the keyboard (every part if split keyboard)
2. Connect the keyboard part
3. Push the flash button on the Arduino controller
4. Test if the keyboard is connected correctly: `ll /dev/tty.*` should return file similar to `/dev/tty.usbmodem14101`
5. Run the cli `sudo avrdude -p atmega32u4 -c avr109 -U flash:w:/Users/soriyath/Documents/dev/qmk/bfo-9000/keebio_bfo9000_fr-ch.hex:i -P /dev/tty.usbmodem14101 -C avrdude.conf`

