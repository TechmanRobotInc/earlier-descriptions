# __Earlier TM ROS1 descriptions vs moveit_config__

Here are the simple descriptions and moveit_config packages (group name = "manipulator") provided earlier.<br/>
> &rArr; Please see the section described in the __Deprecation Notice__ below.<br/>

## __Usage__
The user must first install the TM ROS1 driver, then place the downloaded necessary packages in the correct path of the TM ROS1 driver directory, and finally build all the packages and source 'setup.bash' in the workspace to make the workspace visible to ROS and make it can be used normally.<br/>
<br/>
The following are two ROS1 introductions to the __TM ROS Driver__.<br/>
[_TM ROS1 Melodic driver_](https://github.com/TechmanRobotInc/tmr_ros1/) ``[https://github.com/TechmanRobotInc/tmr_ros1/blob/master/README.md] ``<br/>
[_TM ROS1 Noetic driver_](https://github.com/TechmanRobotInc/tmr_ros1/tree/noetic) ``[https://github.com/TechmanRobotInc/tmr_ros1/blob/noetic/README.md] ``<br/>
How to install the TM ROS1 driver? Please refer to the __Installation__ section in the chapter of __2. Feature__.<br/>

### &sect; Update packages and Installation
> Clone this git repository by typing<br/>
> ``git clone https://github.com/TechmanRobotInc/earlier-descriptions.git``<br/>
> After the download is done, move all packages or just move some required packages in this early-descriptions repository to your tmdriver_ws/src and build it to complete the installation.<br/>
> Please refer to the __&sect; Usage with demo code & driver__ _(steps 1 to 4)_ section in the ROS1 introduction of __TM ROS Driver__.
> ```bash
> $ catkin_make
> $ source ./devel/setup.bash
> ```
>> For example, some of the required packages<br/>
>> * __TM5-900 Robot required packages__<br/>
``tm5_description``<br/>
``tm5_900_moveit_config``<br/>
>> * __TM5-700 Robot required packages__<br/>
``tm5_description``<br/>
``tm5_700_moveit_config``<br/>
>> * __TM12 Robot required packages__<br/>
``tm12_description``<br/>
``tm12_moveit_config``<br/>
>> * __TM14 Robot required packages__<br/>
``tm14_description``<br/>
``tm14_moveit_config``<br/>
>> * __TM14 Robot non-vision series required packages__<br/>
``tm14_description``<br/>
``tm14_nonvision_moveit_config``<br/>
>
> Alternatively, the user can use [DownGit](https://downgit.github.io/#/home) to download a specific file from GitHub.<br/>
> First, the user needs to go to the specific folder you want to download, then just copy the link and paste it to the website [DownGit](https://downgit.github.io/#/home) to download the file.<br/>
> Finally move the downloaded files to your tmdriver_ws/src and build it to complete the installation.<br/>
>> For example, download the required files for TM5-900 Robot<br/>
>> * __TM5-900 Robot required packages's URL__<br/>
``https://github.com/TechmanRobotInc/earlier-descriptions/tree/master/tm5_description``<br/>
``https://github.com/TechmanRobotInc/earlier-descriptions/tree/master/tm5_900_moveit_config``<br/>
>>
>> Copy the link given above and paste it to the website [DownGit](https://downgit.github.io/#/home) to download these specific files.<br/>
> 
### &sect; MoveIt usage with earlier launch instructions
> __ROS1 driver usage__
> 
> After the user has set up the ROS1 environment and built the TM driver based on the specific workspace, please enter your workspace `<workspace>` by launching the terminal, and remember to make the workspace visible to ROS.
>
> __Usage with MoveIt__ 
>
> See [Moveit tutorial](http://docs.ros.org/en/melodic/api/moveit_tutorials/html/doc/getting_started/getting_started.html).<br/>
>
> To bring up the MoveIt environment in simulation mode with a virtual TM Robot (Example: TM5-900), by typing
>
>
> ```bash
> roslaunch tm5_900_moveit_config tm5_900_moveit_planning_execution.launch sim:=True
> ```
>
> Or with virtual TM Robot (Example: TM5-900 non-vision series), by typing
>
>
> ```bash
> roslaunch tm5_900_nonvision_moveit_config tm5_900_moveit_planning_execution.launch sim:=True
> ```
>
> The user can also manipulate TM Robot (Example: TM5-900) in the real world, by typing<br/>
> :bulb: Do you prepare the __TM Robot__ ready ? Make sure that TM Robot's operating software (__TMflow__) network settings are ready and the __Listen node__ is running.  
>
> ```bash
> roslaunch tm5_900_moveit_config tm5_900_moveit_planning_execution.launch sim:=False robot_ip:=<robot_ip_address>
> ```
>
> Or TM Robot (Example: TM5-900 non-vision series), by typing
>
> ```bash
> roslaunch tm5_900_nonvision_moveit_config tm5_900_moveit_planning_execution.launch sim:=False robot_ip:=<robot_ip_address>
> ```
>
> The parameter `<robot_ip_address>` means the IP address of the TM Robot.<br/>
>:warning:[CAUTION] This demo will let the real TM Robot move, please be careful.<br/>

## __Deprecation Notice__
> The older TM ROS1 descriptions and moveit_config packages are no longer actively maintained.
>> :bulb: Tip: We now use the tm_description and corresponding moveit_config packages (group name ="tmr_arm") instead and recommend that users use the Python script <sup>1</sup> to replace the nominal robot model with the specific kinematic parameters from your local TM Robot.<br/>
> <sup>1</sup> For more detailed information, please refer to the __6. TM Robot corrected kinematics value loading and robot description file generation__ chapter in the ROS1 introduction of __TM ROS Driver__.
