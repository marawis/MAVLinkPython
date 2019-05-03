# MAVLinkPython
This code works with Mission Planner. 
Mission Planner created by Michael
Oborne, does a lot more than its name.

Running SITL (Software in The Loop) steps :

1. On terminal, type this command : dronekit-sitl copter --home=-6.9753508,107.6300206,0,180 

      where –home is to set home location (latitude,longitude,altitude,yaw). 
      This command create a virtual vehicle. SITL starts and waits for TCP connections on 127.0.0.1:5760.

2. Open another terminal, and run MAVProxy by following command : mavproxy.py --master tcp:127.0.0.1:5760 --sitl 127.0.0.1:5501 --out
127.0.0.1:14550 --out 127.0.0.1:14551

      this command is to forward messages to UDP ports 127.0.0.1:14550 (check the connection string) and
      127.0.0.1:14551. So, share the connection to udp port 14551 for another works and
      the external Ground Station on port 14550.

3. Open the Mission Planner and connect the ground station to the UDP port 14550.
If connection success then the Mission Planner start for getting param.
