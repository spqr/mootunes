# Tuning the Moo's Demodulator Circuit

The demodulator circuit takes analog bits from the air and turns them into
digital bits for the Moo to interpret.  Since the demodulator circuit plays a
key role in every single transmission from the reader, it's important to make
sure it *correctly* maps input signals to output signals.  This directory
contains instructions and tools for use in testing this circuit.

How to attach an oscilloscope to the Moo's demodulator circuit (refer to the
layout diagram in the 'umassmoo' repository):

* Attach one scope channel (call it the "input" channel) to the Moo's ground
  pin and pin XX.

* Attach another scope channel (call it the "output" channel) to the Moo's
  ground pin and pin YY.

* Send signals from a reader (XXX how?)

* Adjust the scope's knobs until you can visually distinguish the input and
  output signals and interpret them by eye.  Remember that the analog signal
  from the reader is FSK.

* XXX what to look for?

The capacitor ZZ adjusts the voltage level that separates a low signal from a
high signal.  XXX what's the present value of capacitor ZZ?  How can we tell
what the ideal value is?
