# Follow line V3

Once the basic PD controller is designed, we can try to make it as robust as possible and stay on the line as much as possible.

## Second PD controller

If we take as an error reference the horizon of the image (height / 2) we will have more reaction time and the changes of rotation will be smoother, but we may encounter situations such as the following:

![](/img1.png)

In these cases we will find that the upper part of the line is centered, but in the lower part it is displaced.

To avoid this problem, a second controller has been implemented that affects the part closest to the car and forces the turn correction so that the nearby part is centered as much as possible.

To do this, we calculate the error at the top and bottom (if detected), we calculate the PD controllers of both zones and add them according to a certain percentage.

With this implementation it is achieved that the car is more focused on the line at the same speed as in previous implementations and also allows us to increase the speed of F1 getting good results.

[![](https://img.youtube.com/vi/PfynKX2xOSI/0.jpg)](https://www.youtube.com/watch?v=PfynKX2xOSI)

