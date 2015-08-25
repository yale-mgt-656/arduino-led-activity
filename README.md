# Yale-MGT656-Arduino-LED-activity.md

The purpose of this activity is to "get your hands dirty" with
computer hardware and code. We'll be using a
[microcontroller](https://en.wikipedia.org/wiki/Microcontroller)
called the [Ardiuno](https://www.arduino.cc/) to control
[light emitting diodes](https://en.wikipedia.org/wiki/Light-emitting_diode) (LED)
via software we write.

## Step one: light up the LED

To get started, let's make sure we can light up a single LED. You'll
need the following supplies, which you should receive from the instructors:

* an [Arduino Uno](https://www.arduino.cc/en/Main/arduinoBoardUno)
* some jumper wires
* a [USB](https://en.wikipedia.org/wiki/USB) A-to-B1 power cable
* some LEDs
* a [breadboard](https://en.wikipedia.org/wiki/Breadboard)

Plug the A-end of your USB into your computer and your B-end into the Arduino to turn on the Arduino. (Don't plug the A-end into anything other than a computer.) Your Arduino should power on.  Now, you want to choose a resistor and wire up your system like shown here

![wire configuration for step 1](https://raw.githubusercontent.com/yale-mgt-656/arduino-led-activity/master/images/one-led-via-5v_bb.png)
![wire configuration for step 1](https://learn.adafruit.com/system/assets/assets/000/002/170/medium800/learn_arduino_overview.jpg?1396780130)

The LED should light up.

Here are some questions you should be able to answer as a group (likely via searching about on the web and discussing among yourselves).

* Where is electricity flowing?
* How much electricity is the Arduino drawing from your computer?
* What does the resistor do?
* What happens if you choose a different resistor?
* How are the resistors different? (Notice their patterns)
* What is different about the LEDs that you have?

## Step 2: blink the LED

The Arduino can be told to do send electricity in varying amounts to the different
outputs on the side of the board. In part one, you used the 5V constant power.
Now, we're going to use the numbered pins. In order to control the power of those
pins, we'll need to write a program for the Arduino and load it onto the Arduino.
To do that, you'll need to download the [Arduino IDE](https://www.arduino.cc/en/Main/Software)
onto your laptop. We'll write a program with the IDE and upload it via the USB cable
onto the Arduino.

Once you've installed the Arduino IDE, you'll want to load up the "blink" example code.
Go to `File > Examples > 01. Basics > Blink` as shown in the following images.

![loading arduino blink example](https://learn.adafruit.com/system/assets/assets/000/002/146/medium800/learn_arduino_opening_blink_example.jpg?1396779947)

You should see some code that looks like this

![arduino blink example code](https://learn.adafruit.com/system/assets/assets/000/002/147/medium800/learn_arduino_ide_blink.jpg?1396779953)

Save your own copy of that code by going to "Save as" or equivalent on your computer. You can call it anything you want, like "mgt656-led-blink".

At the bottom of the window, the IDE should be showing you how it is connected to the Arduino. This may not be correct. It may look like this

![arduino connection information](https://learn.adafruit.com/system/assets/assets/000/002/150/medium800/learn_arduino_bottom_of_ide_showing_board_port.jpg?1396779969)

or

TODO: INSERT IMAGE HERE!

Click on the 'Upload' button. The second button from the left on the toolbar.

![arduino upload button](https://learn.adafruit.com/system/assets/assets/000/002/151/medium800/learn_arduino_upload_button.jpg?1396779976)

You'll see a progress bar as it uploads the code to the Arduino

![uploading](https://learn.adafruit.com/system/assets/assets/000/002/153/medium800/learn_arduino_upload_2_uploading.jpg?1396779984)

It should complete successfully

![upload done](https://learn.adafruit.com/system/assets/assets/000/002/154/medium800/learn_arduino_upload_3_done.jpg?1396779992)

Or, you might get an error if your computer didn't have the right settings to talk to the attached Arduino. If that is the case, you will need to change them. It should be easy, if not a TA can help.

![upload error](https://learn.adafruit.com/system/assets/assets/000/002/155/medium800/learn_arduino_upload_4_failed.jpg?1396779995)

Now, what should you see on the board? You should see a constant red LED if you left your board the same way it was in part one of this activity: it's still plugged into the 5V pin! If you look at the code you uploaded, you'll notice that it is manipulating the power sent to pin 13. See the line that looks like as follows

```processing
int led = 13;
```

In order to control the LED, we'll want to move the wire from the 5v pin to pin 13. Your writing should look roughly as follows
