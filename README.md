# STM32-7Segment-Display
7-segment display interfacing with STM32 using GPIO
# STM32 7-Segment Display using GPIO

## About this project

This is a simple project where I interfaced a 7-segment display with an STM32 microcontroller.

The aim was to understand how each segment of the display can be controlled using GPIO pins and how binary/hex values are used to display numbers.

---

## What I did

* Connected each segment of the 7-segment display to STM32 GPIO pins
* Wrote a function `Printdata()` to control all segments
* Used hexadecimal values to display numbers
* Displayed numbers from 0 to 9 one by one with delay

---

## How it works

A 7-segment display has multiple segments (a, b, c, d, e, f, g).

Each segment is connected to a GPIO pin.
By turning specific pins ON or OFF, different numbers can be displayed.

In the code:

* Each bit of the data represents one segment
* If the bit is 1 → segment turns ON
* If the bit is 0 → segment turns OFF

The function `Printdata()` checks each bit and sets the corresponding GPIO pin.

---

## Example

Some values used in the code:

* `0x3F` → displays 0
* `0x06` → displays 1
* `0x5B` → displays 2
* `0x4F` → displays 3

These values decide which segments should glow.

---

## Program flow

1. Initialize GPIO
2. Enter infinite loop
3. Send hex values one by one
4. Add delay between each number
5. Repeat continuously

---

## Pin connections (based on code)

The segments are connected to different GPIO pins:

* PA10, PA8, PA9
* PB3, PB4, PB5, PB10
* PC7

(Each pin controls one segment)

---

## What I learned

* How 7-segment displays work
* Using GPIO pins in STM32
* Bitwise operations in C
* How hardware reacts to binary data

---

## Output

The 7-segment display shows numbers from 0 to 9 continuously in a loop.

---

## Small issue I noticed

* The value for digit 6 can be improved (`0x7C` → usually `0x7D`)
* Digit 7 (`0x07`) is missing in sequence

This can be corrected for proper display.

---

## Possible improvements

* Add support for multiple digits using multiplexing
* Display custom patterns
* Take input from button or sensor
* Reduce delay for smoother transition

---

## Tools used

* STM32CubeIDE
* STM32 HAL Library

---

## Note

This is a beginner-level project, but it gave me a clear understanding of how microcontrollers control external devices using simple logic.

