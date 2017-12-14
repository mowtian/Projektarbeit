# Projektarbeit
> ## zed camera
> ```js
> catkin_make   
> source ./devel/setup.bash    
> roslaunch zed_wrapper zed.launch
> roslaunch zed_wrapper display.launch   
> ```

> ## Scanse
> ```js
> ll /dev/ttyUSB0   
> sudo chmod 666 /dev/ttyUSB0   
> sudo usermod -aG dialout pc-241  
> ```

> ```js
> roslaunch sweep-ros-master sweep2scan.launch   
> ```

> ```js
> rosbag record -a   
> rosbag play recorded1.bag recorded2.bag    
> rosbag play --clock recorded1.bag   
> rosbag play --clock --hz=200 recorded1.bag    
> rosbag play -d 5 recorded1.bag    
> rostopic echo -b <BAGFILE>.bag -p /LaserScan > <output>.csv     
> rostopic echo -b <BAGFILE>.bag -p /LaserScan > <output>.txt     
> ```

> ## Gmapping
> ```js
> rosrun gmapping slam_gmapping scan:=LaserScan    
> rosrun map_server map_saver -f mymap    
> ```

> ## backup
> ```js
> sudo su    
> cd /    
> tar cvpzf backup.tgz --exclude=/proc --exclude=/lost+found --exclude=/backup.tgz --exclude=/mnt --exclude=/sys --exclude=/media /   
> ```

> ```js
> sudo tar xvpfz backup.tgz      
> sudo mkdir proc lost+found mnt sys media           
> ```
