# pypilot_conversion
Details of converting a ST1000/ST2000 tiller pilot into a PyPilot implementation.

Work in progress; details follow in due time. Based on a prototype described here https://forum.openmarine.net/showthread.php?tid=1864&pid=9664#pid9664

To be used in combination with pypilot_ray replacing pypilot_hat.

https://github.com/marcobergman/pypilot_ray

![image](https://user-images.githubusercontent.com/17980560/174496239-032a153d-76ff-4484-ad62-f275af7a08e0.png)

Build notes:

- Had to flip one resistor on the keyboard to the front; otherwise it was in the way of a piece of the plastic casing. Also had to tilt the buckdown converter to its side.
- The motor board has one fault on it: the A3 input had to be tied to +5V, otherwise the controller thinks the motor is 170°C and would not move. Solved by cutting the pin 22 off the arduino and putting a resistor between arduino pins 22 and 27.
- The current measuring is still a bit in progress. The Pololu CS (current sense) pin is supposed to give 'about 20 mV/A plus a 50 mV offset', but setting the servo.current.factor and .offset was not enough; I tweaked motor.ino a bit but don't get a linear reading so far.

First findings impression: https://www.youtube.com/watch?v=vbth_teGMJA

Images from the building process: https://photos.app.goo.gl/vQ7VHdccvfHCTUkM7
