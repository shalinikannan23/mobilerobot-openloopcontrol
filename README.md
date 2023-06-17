## Aim:

## To develop a python control code to move the mobilerobot along the predefined path.
Equipments Required:

    RoboMaster EP core
    Python 3.7

## Procedure

## Step1:

## Use from robomaster import robot.

## Step2:

Choose the x,y,z - axis movement distance(meters).

## Step3:

Give ep_chassis.move to move straight.

## Step4:

Give time.sleep() for a break.

## Step5:

Give ep_chassis.drive_speed to have a circular movement.
## Program:
```
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
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=100,b=0,effect="on")  
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=0,b=0,effect="on")  
    time.sleep(2)
    ep_chassis.move(x=2, y=0, z=0,xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=255,b=0,effect="on")  
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=0,g=255,b=255,effect="on")  
    time.sleep(2)
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=102,b=0,effect="on")  
    ep_chassis.move(x=0, y=0, z=-90, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=255,g=153,b=204,effect="on")  
    time.sleep(2)
    ep_chassis.move(x=2, y=0, z=0, xy_speed=1).wait_for_completed()
    ep_led.set_led(comp="all",r=153,g=204,b=0,effect="on")  

    ep_camera.stop_video_stream()
    print("Stopped video streaming.....")

    ep_robot.close()
```
## MobileRobot Movement Image:

![robomaster](https://github.com/shalinikannan23/mobilerobot-openloopcontrol/assets/118656529/283aeaa4-da84-447c-a6e2-42a08ad04a4f)

![245717585-2ce8adfd-8499-426a-950a-eeaf6937a5ea](https://github.com/shalinikannan23/mobilerobot-openloopcontrol/assets/118656529/82bc3c29-b9e6-4de6-8bf8-6680e15c1e3a)

MobileRobot Movement Video:

Youtube Link : (https://youtu.be/AfWMcAk0HtY)
## Result:

Thus the python program code is developed to move the mobilerobot in the predefined path.
```
Mobile Robotics Laboratory
Department of Artificial Intelligence and Data Science/ Machine Learning
Saveetha Engineering College
```
