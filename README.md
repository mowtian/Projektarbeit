# Projektarbeit
##zed camera
catkin_make
source ./devel/setup.bash

##Scanse
ll /dev/ttyUSB0
sudo chmod 666 /dev/ttyUSB0
sudo usermod -aG dialout pc-241
roslaunch sweep-ros-master sweep2scan.launch
rosbag record -a
rosbag play recorded1.bag recorded2.bag
rosbag play --clock recorded1.bag
rosbag play --clock --hz=200 recorded1.bag
rosbag play -d 5 recorded1.bag

##backup
sudo su
cd /
tar cvpzf backup.tgz --exclude=/proc --exclude=/lost+found --exclude=/backup.tgz --exclude=/mnt --exclude=/sys --exclude=/media /

sudo tar xvpfz backup.tgz
sudo mkdir proc lost+found mnt sys media
