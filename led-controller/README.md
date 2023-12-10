# ESPHome LED Controller

Controls either individually addressible or single-color "dumb" LED strips, with an optional button or rotary encoder.
This means I effectively get four different controller options in one PCB order.

It can use either 12V or 5V LED strips, running the controller off the same power supply as the LEDs.

### WARNING: I didn't properly engineer this, so I don't know how much current it can safely push. Use at your own risk.

### Variants

Depending on the configuration, different parts must be printed and different components soldered to the board:

**Input**: Solder either the push-button or the rotary encoder, and print the appropriate covers for the housing.

**Output**: Solder either:
- the mosfet U1 for PWM control of "dumb" LEDs or
- the resistor R6 and the jumper JP1 for controlling individually addressible LEDs.

Depending on the configuration chosen, the firmware must be modified as well. See the comments in `firmware.yml`.

NOTE: I had to rip out some of the reference models from the Fusion 360 CAD drawings because I don't have the rights to them.
This leaves the references all jumbled, sorry about that.
