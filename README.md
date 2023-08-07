# LEGO® Spike Hub and the Distance Sensor

A Python snippet utilizing the LEGO Spike distance sensor, [MicroPython](https://lego.github.io/MINDSTORMS-Robot-Inventor-hub-API/), and the `get_distance_cm()` and `light_up()` commands.

## Sample Code

```py
from mindstorms import MSHub, Motor, MotorPair, ColorSensor, DistanceSensor, App
from mindstorms.control import wait_for_seconds, wait_until, Timer
from mindstorms.operator import greater_than, greater_than_or_equal_to, less_than, less_than_or_equal_to, equal_to, not_equal_to
import math

hub = MSHub()

distance_sensor = DistanceSensor('A')

pixels = '00000:00000:00000:00000:00000'

while True:

    dist_cm = distance_sensor.get_distance_cm()
    dist_inches = distance_sensor.get_distance_inches()

    if equal_to(dist_cm, None):
        pass

    elif less_than(dist_cm, 5):
        pixels = '99999:99999:99999:99999:99999'

    elif less_than(dist_cm, 10):
        pixels = '88888:88888:88888:88888:88888'

    elif less_than(dist_cm, 15):
        pixels = '77777:77777:77777:77777:77777'

    elif less_than(dist_cm, 20):
        pixels = '66666:66666:66666:66666:66666'

    elif less_than(dist_cm, 25):
        pixels = '55555:55555:55555:55555:55555'

    elif less_than(dist_cm, 30):
        pixels = '44444:44444:44444:44444:44444'

    elif less_than(dist_cm, 35):
        pixels = '33333:33333:33333:33333:33333'

    elif less_than(dist_cm, 40):
        pixels = '22222:22222:22222:22222:22222'

    elif less_than(dist_cm, 45):
        pixels = '11111:11111:11111:11111:11111'

    else:
        pixels = '00000:00000:00000:00000:00000'
        
    hub.light_matrix.show(pixels)
    print(dist_cm)

    if hub.left_button.is_pressed() and hub.right_button.is_pressed():

        break

hub.speaker.beep()
```

***

## Repo Resources

* [Visual Studio Code](https://code.visualstudio.com/)
* [MicroPython for LEGO Robot Inventor](https://www.lego.com/en-ca/themes/mindstorms/downloads)
* [LEGO Mindstorms](https://www.lego.com/en-ca/themes/mindstorms)
* [LEGO Mindstorms App for Mac](https://apps.apple.com/us/app/lego-mindstorms-inventor/id1515448947)
* [LEGO Mindstorms App for Android](https://play.google.com/store/apps/details?id=com.lego.retail.mindstorms)
* [LEGO Mindstorms App for Windows](https://www.microsoft.com/store/apps/9N7GN3KC2GK6)

<a href="https://codeadam.ca">
<img src="https://codeadam.ca/images/code-block.png" width="100">
</a>


