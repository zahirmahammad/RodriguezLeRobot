### Initial Setup

This is where we calibrate the LeRobot Leader and Follower arms, this is done only once at the beginning of the setup

**Step 1:**

First find the port names of the Leader and Follower

- Make sure both the Leader and Follower arms are connected to the Jetson 
- Run this and follow the instructions it shows
```
lerobot-find-port 
```

- Keep a Copy of both ports
- Current ports (may change sometimes) 
    - Leader Arm: ```/dev/ttyACM1```
    - Follower Arm: ```/dev/ttyACM0```


**Step 2:** 

Calibrate Leader Arm
```
lerobot-calibrate --teleop.type=so101_leader --teleop.port=/dev/ttyACM1 --teleop.id=my_awesome_leader
```
- Follow the instructions


Calibrate Follower Arm
```
lerobot-calibrate --robot.type=so101_follower --robot.port=/dev/ttyACM0 --robot.id=my_awesome_follower
```
- Follow the instructions


**Step 3:** 

Teleoperate LeRobot
```
lerobot-teleoperate --robot.type=so101_follower --robot.port=/dev/ttyACM0 --robot.id=my_awesome_follower --teleop.type=so101_leader --teleop.port=/dev/ttyACM1 --teleop.id=my_awesome_leader
```
