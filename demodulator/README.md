# Tuning the Moo's Demodulator Circuit

The demodulator circuit takes analog bits from the air and turns them into
digital bits for the Moo to interpret.  Since the demodulator circuit plays a
key role in every single transmission from the reader, it's important to make
sure it *correctly* maps input signals to output signals.  This directory
contains instructions and tools for use in testing this circuit.

How to attach an oscilloscope to the Moo's demodulator circuit (refer to the
layout diagram in the 'umassmoo' repository):

* Attach one scope channel (call it the "input" channel) to the Moo's ground
  pin and pin 4 of chip U1. This pin is the analog signal of input bits.

* Attach one scope channel (call it the "bit power" channel) to the Moo's
  ground and pin 3 of chip U1. This pin is the voltage level to distingush bit
  0 and bit 1 of input channel

* Attach one scope channel (call it the "output" channel) to the Moo's
  ground pin and pin 1 of chip U1. This pin is the comparing result of input
  channel and bit power channel.

* Attach one scope channel (call it the "recieved" channel) to Moo's ground pin
  and `RECEIVE` pin. This is the output pin of level translator with output
  channel as the input.

* Send signals from a reader. It does not matter much what the signals are when
* debugging the demodulator. All that you are trying to do is confirm that 0's
* and 1's are reliably different. Any reader+application will do.

* Adjust the scope's knobs until you can visually distinguish the input and
  output signals and interpret them by eye.  Remember that the analog signal
  from the reader is PIE (Pulse Interval Modulation). For a reference on this,
	see: http://rfidsecurity.uark.edu/downloads/slides/mod04_lesson04_slides.pdf

* Compare the signals of input channel, output channel and received channel to
  see whether the bit streams are same. If the bit streams are not the same, you
	will have to tune the bit power channel to correct this. 

* The capacitor C2 adjusts the voltage level that separates a low signal from a
high signal.  The present value of capacitor is 0.1uF.  Once the change of
capacitor value renders more mismatches of bit streams of the input, output,
and received channels, the ideal value of the capacitor is found.
