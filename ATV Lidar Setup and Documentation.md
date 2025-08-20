1.Henry Haight

_University of Washington Bothell_

<henryh73@uw.edu>

**_Abstract—The purpose of this document is to describe how to operate the YDLidar for the Autonomous ATV. This includes setup instructions and written explanations for the functions used by the lidar to detect objects._**

Keywords—template, UWB Electronics Club, format

# Features

- Setup
- Functions
- Quirks of the YDLidar
## Setup

Download the SDK driver for \[YDLIDAR\](<https://github.com/YDLIDAR/YDLidar-SDK/tree/master>)

Check the Linux machine has:

- swig
- python
- openpyxl
- pandas
- cmake
- matplotlib
- Follow the \[instructions for installation on the YDLIDAR Github page\](<https://github.com/YDLIDAR/YDLidar-SDK/blob/master/doc/howto/how_to_build_and_install.md>)
- Open 'YDLidar-SDK/python/examples/plot\\\_tof\\\_test.py' and change line 26 to this: 'laser.setlidaropt(ydlidar.LidarPropSerialBaudrate, 128000\\)'
- Run Test '$ cd YDLidar-SDK/python/examples/ $ python plot\\\_tof\\\_test.py'

## Functions

animate(num)

This function is the main function of the LIDAR code. This creates 3 arrays and uses them to append the 3 major components of the LIDAR signal: angle, range, and intensity. These arrays are added to using the YDLidar scan function, which then adds them to each array every pass of the LIDAR. This is then graphed at the end of the function after passing through the other 2 functions, which determine which signals are objects.

The intensity is always set at 10, so it is useless for our application. This seems to be a quirk of the YDLidar API. The angle is measured in radians. Range seems to be measured in feet.

find_close_sequences(angle, threshold=, ran)

This finds where the sequences are close and returns arrays where there are points that are close, so we can fit a line between 3 points of those arrays in graph_points

graph_points(sequences)

Finds the midpoints, start, and end of the 2D array, which is then returned as one array so it can be graphed

## Quirks of the Lidar

To use your own code place the file you want to modify or make in YDLidar-SDK/python/examples/. This allows the lidar to find the library it needs to start and call the lidar.
