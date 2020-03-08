# Follow line V2

Once the P controller has been implemented, we can try to solve its main drawback (strong oscillations) by adding a second "variable".

## PD Controller
To solve the strong oscillations suffered by the P controller, we are going to add a new term to our address correction that takes into account the error in the previous iteration.

To do this we will simply add a new global variable that allows us to store the previous error and calculate the difference from the current error.

Once we have this difference we will affect our correction in a certain percentage.

In this way our controller will act differently if the error is increasing or if it is decreasing.

IMPORTANT !: Remember to update the previous error in each new iteration.

## Rediscovering the line
It is possible that at some point our F1 loses the line it is following, so we must decide what to do in this situation.

In this implementation a solution has been developed taking into account the error of the previous iteration.

If we lose the line and in the previous iteration the error indicated that we should turn right we will turn right until we locate the line.

We must be careful with this solution since it is possible that our F1 finds the line in the opposite direction and does not complete the round.

Although this implementation offers better results than the previous one, they are still neither robust enough nor offer low times.

[![](https://img.youtube.com/vi/iY22_ikCO6Q/0.jpg)](https://www.youtube.com/watch?v=iY22_ikCO6Q)