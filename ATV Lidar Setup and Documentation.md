## Setting up YDLIDAR

* Download the SDK driver for [YDLIDAR](https://github.com/YDLIDAR/YDLidar-SDK/tree/master)  
* Check the Linux machine has   
  * swig  
  * python  
  * openpyxl  
  * pandas  
  * cmake  
  * matplotlib  
* Follow the [instructions for installation on the YDLIDAR Github page](https://github.com/YDLIDAR/YDLidar-SDK/blob/master/doc/howto/how_to_build_and_install.md)  
* Open 'YDLidar-SDK/python/examples/plot\_tof\_test.py' and change line 26 to this: 'laser.setlidaropt(ydlidar.LidarPropSerialBaudrate, 128000\)'  
* Run Test '$ cd YDLidar-SDK/python/examples/ $ python plot\_tof\_test.py'

## Creating your own code

* Place the file you want to modify or make in YDLidar-SDK/python/examples/. This allows the lidar to find the library it needs to start and call the lidar.

## Obstacle Detection