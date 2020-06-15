> A minimalist guide to  a few frameworks⁠—on Ubuntu and Vector computing⁠—for the person who was born yesterday
>> Written by a novice for the novice

# Part 4 - Building and Customizing AirSim

The following instructions are for a fresh install of Ubuntu 18.04 LTS 64-bit on a Lenovo P52 (i7-8850H/Quadro P2000)

Everything after a `$` is entered on a terminal; everything after `>>>` is passed to a Python interpreter



--------------
--------------
--------------




## Headless AirSim on a remote server

TBD, ideally on Vector's cluster
example of distributed RL with Azure
https://github.com/microsoft/AutonomousDrivingCookbook/tree/master/DistributedRL



## Modifying AirSim

code structure
https://microsoft.github.io/AirSim/code_structure/

review the `.bat` and `.sh` scripts
https://microsoft.github.io/AirSim/dev_workflow/

essentially, build.sh copies the useful files to Blocks

> For Linux, make code changes in AirLib or Unreal/Plugins folder and then run ./build.sh to rebuild. This step also copies the build output to Blocks sample project. You can then follow above steps again to re-run.
https://microsoft.github.io/AirSim/unreal_blocks/

the FAQs are Windows/Visual Studio based
contemplate VS Code (?) https://code.visualstudio.com/docs/?dv=linux64_deb

### New Python APIs

example
https://github.com/Microsoft/AirSim/commit/f0e83c29e7685e1021185e3c95bfdaffb6cb85dc

### New C++ APIs

add printout of date of the most recent compilation

### Tuning `simpleflight` flight controller

https://microsoft.github.io/AirSim/flight_controller/ / https://microsoft.github.io/AirSim/simple_flight/

> We thus view flight controller simply as collection of algorithms packaged in a library. Another key emphasis is to develop this code as dependency free header-only pure standard C++11 code.

> Internally simple_flight uses cascade of PID controllers to finally generate actuator signals. 

> Please note that simple_slight currently doesn't support state estimator which means estimated and ground truth kinematics values would be same for simple_flight.

> We plan to add complimentary filter based state estimation for angular velocity and orientation using 2 sensors (gyroscope, accelerometer) in near future. In more longer term, we plan to integrate another library to do velocity and position estimation using 4 sensors (gyroscope, accelerometer, magnetometer and barometer) using EKF. If you have experience this area than we encourage you to engage with us and contribute!

> simple_flight uses steppable clock by default which means clock advances when simulator tells it to advance (unlike wall clock which advances strictly according to passage of time). Otherwise add `"ClockType": "ScalableClock"`

recompiling airsim
https://github.com/microsoft/AirSim/tree/master/AirLib/include/vehicles/multirotor









## Custom Unreal Engine 4 environments

needs Epic Games Launcher (Windows, macOS?) to create and Unreal project folder
https://microsoft.github.io/AirSim/unreal_custenv/

then just copy it over to your Linux machine (how many of the steps above can we move to Ubuntu?)


add notes on Updating Your Environment to Latest Version of AirSim

## Customizing the drone model

https://microsoft.github.io/AirSim/custom_drone/

### pyhsics and 3D model

use own model
https://microsoft.github.io/AirSim/settings/#pawnpaths

from 2017: https://github.com/Microsoft/AirSim/wiki/hexacopter
- use the same model
- does the physics code still exists?

For cars, we support only PhysX for now (regardless of value in this setting). For multirotors, we support "FastPhysicsEngine" only.










## Create new binaries

For custom environment/airsim
at once ore in separate steps?
TBD


















## (optional) ROS installation from source

TBD, if needed

## (alternative) Docker installation

TBD, if needed https://github.com/Microsoft/AirSim/blob/master/docs/docker_ubuntu.md
TBD

## (optional) PX4 flight controller

### SITL

https://microsoft.github.io/AirSim/px4_sitl/ /  https://microsoft.github.io/AirSim/px4_build/

px4 and mavlink
- https://github.com/Microsoft/AirSim/wiki/Intercepting-MavLink-messages
- https://microsoft.github.io/AirSim/px4_logging/
- https://microsoft.github.io/AirSim/mavlinkcom/

### HTIL 

left for later

with xbox controller https://microsoft.github.io/AirSim/xbox_controller/
on linux https://microsoft.github.io/AirSim/remote_control/
see "RC" under vehicle in `settings.json`

https://microsoft.github.io/AirSim/px4_setup/
