MobileRobot-Openloopcontrol

Aim:
To develop a python control code to move the mobilerobot along the predefined path.

Equipments Required:

 1.RoboMaster EP core
 2.Python 3.7
 
Procedure

Step1: Initiate the MobileRobot.

Step2: Connect your PC with the MobileRobot.

Step3: Open Python program.

Step4: Program the movements of the robot using python code.

Step5: Execute the python program.

Program
```
Python control code to move the mobilerobot along the predefined path.
Developed by: K.SANTHANA LAKSHMI
Register No.: 212222240091
from robomaster import robot
import time
from robomaster import camera

if _name_ == '_main_':
    ep_robot = robot.Robot()
    ep_robot.initialize(conn_type="ap")

    ep_chassis = ep_robot.chassis
    ep_led = ep_robot.led
    ep_camera = ep_robot.camera
    
    print("Video streaming started.....")
    ep_camera.start_video_stream(display=True, resolution = camera.STREAM_360P)
    ''' 
    x = x-axis movement distance,( meters) [-5,5]
    y = y-axis movement distance,( meters) [-5,5] 
    z = rotation about z axis ( degree)[-180,180]
    xy_speed = xy axis movement speed,( unit meter/second)  [0.5,2]

    '''
    ep_chassis.move(x=0, y=0, z=60, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=255,b=0,effect="on") 
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=102,b=255,effect="on") 
    ep_chassis.move(x=0, y=0, z=120, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=51,g=51,b=255,effect="on") 
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_chassis.move(x=0, y=0, z=120, xy_speed=1).wait_for_completed()
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_chassis.move(x=0, y=0, z=180, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")
    ep_chassis.move(x=2, y=0, z=60, xy_speed=1).wait_for_completed()
    
    
   




 
    
    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```
MobileRobot Movement Image:
robo

![Screenshot (420)](https://github.com/santhanalakshmi04/mobilerobot-openloopcontrol/assets/119475762/67ad8ca2-88a9-46b0-8e9a-a155872536e6)

Start Point:

![Screenshot (421)](https://github.com/santhanalakshmi04/mobilerobot-openloopcontrol/assets/119475762/e6dc100e-146e-4d07-bb85-69804076fd9b)

End Point:

![Screenshot (422)](https://github.com/santhanalakshmi04/mobilerobot-openloopcontrol/assets/119475762/f09598b2-0837-4d0f-98ea-cf1934d0346d)


MobileRobot Movement Video:
Upload your video in Youtube and paste your video-id here https://youtu.be/8izJj4B58IU

Result:
Thus the python program code is developed to move the mobilerobot in the predefined path.

Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
