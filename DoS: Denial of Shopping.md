DoS: Denial Of Shopping
======

> Author: *Joseph Gabay*

---

> Armand Alvarez

> 07 August 2021

> github.com/Armand-Alvarez

---

Shopping cart security wheels

* Invisible fence, for carts

* When taking a cart outside a boundry, wheel locks itself

# How do they work

* Magnetic loop system - underground perimeter wire sends out signal

* When cart crosses signal, internal mechanism locks wheel

* Employees can come out and unlock wheel

* Wheel has 3V lithium battery

* DC motor

* PCBa hosts radios and microcontroller

	* 2 separate antennas
		1. 2.4G - PCB Trace
		2. 7.8K - Inductor
	* TI CC2510 Microcontroller - low power standby mode optimal
	* Motor driver circuit
	* VLF Amplifier
	* JTAG port for programming chip

# How do we learn more about the lock signal?

* FCC.gov - any consumer product that has RF systems must be approved by FCC

* Patent searches

* Other hackers

	* tmplab.org

# What did we learn?

* two control frequencies

	* Low freq is below 9 KHz
	* Uses MSK or FSK

# Capturing the VLF Signal - Problems

* Signal is very low frequency (VLF) - <9KHz

	* Very difficult to build antenna to pick up on this

	* 9 KHz is in audio range

		* You can use audio amp equipment

# How he picked up the signal

* Built homemade contraption

	* Loopstick antenna - ferrite core with magnet wire looped around it

	* 3.5mm Jack with 2.5 kOhm resistor to trick audio port into thinking it is a microphone

Plug it into the phone and plop it on the line underground and you can pick up the signal

Looking at the wave signal, you can see it is an 8-bit signal composed of 10 parts

	* There is a start bit - signals MC that signal is staritng
	
	* Series of long or short blips - 1's or 0's

	* After 8 of those, you have a long blip that tells MC it is done

## This locks a shopping cart. What about unlocking one?

Looking at the unlock signals, we see unlock signal is just inverse of lock signal

# Will a 7.8 KHz replay attack work?

* The signal is always the same for the locking carts, no incrementing or anything

* You can do this w/o an antenna, you can use phone speaker or something as a really crappy antenna, it sends signals producing sound.

	* Play mp3 on phone to unlock - produces EMF 

To increase the range you would need a bigger coil, external amplifier, but to double the range you need to quadrouple the resources. It is diminishing returns.

# Looking at the 2.4 GHz Signal

* Much easier to work with

You can import to Audacity and play the .wav file through HackRF and it works.

	* Gives a range that works from across the room (unlocking)

Trying the different lock signal possibilities (3 bits of binary combinations), none worked. Likely a built-in security measure.

# So what can you do with this?

* Short range locking of carts

* Unlocking carts that have been locked

* Be content with the knowledge you have learned
