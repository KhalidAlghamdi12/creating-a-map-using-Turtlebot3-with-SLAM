# creating-a-map-using-Turtlebot3-with-SLAM

First you have to install Turtlebot3 on your ubunto original GUID --> https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/

After installing please make sure to expose these types on the picture because it may cause errors if you didn't (on bashrc)
if you don't have it go to files and click ctrl+h to show hidden files 

after that you need a folder for work space as always --> $cd catkin_ws (mkdir if you don't have a file already)

then on the catkin_ws type : 
$ source devel/setup.bash

then 

$ export TOURTLEBOT3_MODEL=waffle_pi  <-- this is the model i tried
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping 

to install slam_gmapping
create a catkin workspace:

mkdir -p catkin_ws/src
cd catkin_ws/src
source /opt/ros/<DISTRO>/setup.bash
catkin_init_workspace
clone the repository:

git clone https://github.com/ros-perception/slam_gmapping.git
compile the workspace

cd ..
catkin_make
source the workspace

source devel/setup.bash

It should work fine if you install all the necessary packages 

To save the map : 

Launch the map_saver node in the map_server package to create thefiles...

$ rosrun map_server map_saver -f ~/map   (-f  specifies a folder location and a file name where files to be saved)

it should look like the map on the picture 

the white area is collision free  .. the black area is occupied.. the gray area represents the unknown area

thanks for reading
