# Follow Line
JdeRobot F1 practice

## First Approach (24/02/2020)
The first problem we have to face is deciding if we are centered in the lane or we must correct the direction of the car. For this we will use the red line that marks the center of the route.

The first thing that has been done is to obtain the position of the line with respect to the image. For this, a color filter has been used, a row has been selected from the bottom of the image and the positions in which the values ​​are greater than 0 have been obtained, that is, it is white. In this way we obtain the position of the red line.

Once the position of the line in the image is calculated, we must check if we are centered on it, or on the contrary, we must correct the direction. To do this, we will calculate the central position of the line from the previously calculated positions and check the distance to the midpoint of the image.

This difference between the midpoint of the image and the midpoint of the line will be the error we will use for the controller.

### P controller
As a first approximation we can create a P controller in which we will only take into account the error of the current iteration.

Using this implementation we will force our F1 to rotate a bit of the calculated error.

The main problem of this implementation is the strong oscillation between one position and the next when the F1 tries to correct its direction, so if we want to stay centered on the line the speed cannot be very high.


[![](http://img.youtube.com/vi/BIow3qinfL0/0.jpg)](https://www.youtube.com/watch?v=EPQRAjrvLv0&feature=youtu.be "Follow Line V.1")