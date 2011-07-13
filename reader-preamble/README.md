# Using the reader's preamble to tune Moo's receive timing

According to section XX of the C1G2 specification, the reader sends a preamble
before each YY.  A tag is supposed to use this preamble to adjust its notion of
timing.

The reader's preamble consists of two messages, each of which has a different
length because the reader-to-tag downlink uses FSK.

* "Here's what a 0 looks like"

* "Here's what a 1 looks like"

The tag can measure the width of each message and adjust its timing
accordingly.  In the case of the Moo, which uses its built-in timer interrupt
facility to make sure it wakes up at the right times to process bits, preamble
measurements should be used to adjust the values that go into the timer's
capture-and-compare register when the Moo is about to go to sleep.
