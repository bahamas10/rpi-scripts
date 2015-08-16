rpi-scripts
===========

Scripts for the raspberry pi and the GPIO pins

Dependencies
------------

Run `./install-deps` (it will call `sudo` when needed) to install both
dependencies:

- [wiringPi](http://wiringpi.com/the-gpio-utility/) - for the `gpio` utility
- [Adafruit Python DHT Library](https://github.com/adafruit/Adafruit_Python_DHT) - for the `dht` script

They will be checked out with `git` to ~/dev

Note: every script, unless otherwise specified, takes pin numbers in the wiringPi
numbering system.

Scripts
-------

### `dht`

A slightly modified version of the Adafruit DHT script to output temperatures
in both farenheit and celsius, in a more machine friendly way.

    $ sudo ./dht 22 17
    temperature farenheit: 78.1F
    temperature celsius: 25.6C
    humidity: 47.8%

Pin numbers must be specified in BCM format

### `pin-flip`

Flip a pin HIGH then LOW for 1 (or variable) second.  This will result in the pin
being set to OUT.

    $ ./pin-flip 1
    turning on... done.
    turning off... done.

Useful for testing LEDs or relays.

### `pin-input-status`

Monitor a pin (every 1/4 second by default) for signal changes from HIGH to LOW or
vice-versa.  `HIGH` or `LOW` will be written and updated on stdout.

    $ ./pin-input-status 2
    LOW ^C

Ctrl-C to exit

### `pin-switch-status`

Same as above but with ASCII art - looks great with reed switches.

    $ ./pin-switch-status 2
    opened |------------|        |------------|^C

License
-------

MIT License
