## Setting up

- Print, or have someone print the box and lid.
- Aquire a 9 gram SG90 servo and a NodeMCU Amica (a Lolin does not (yet!) fit the current box design).
- Cut one of the horns of the servo to length. In the locked position it should stick out a little through its slot so it goes inside the lid when locked.
- Flash the MCU.
- Connect the servo to the MCU. Brown to GND, red to 3v3, orange to D4.
- Pull the power wires through the hole in the bottom of the box and connect 5v (red) to Vin and ground (black) to GND. (See the power heading below.)
- Connect to the box' wifi AP and have it connect to your network.
- With everything outside of the box, do a test run.
  - Make sure the horn is in a neutral position.
  - Lock the box.
  - Verify that the horn is now in the correct rotation to stop the lid from lifting off.
  - Open the box with the password in the newly created txt file.
- If there are no issues, the assembly can be pushed into the box in a gentle manner. Make sure the side of the MCU with the power wires is on the side of the box with the hole.

Not all 9g servos are the same. If the horn moves too much (only about 90 degrees is necessary) then the open- and closed postion can be adjusted using the controller.
