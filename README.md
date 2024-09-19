# ROSbot XL ROS

ROS2 packages for ROSbot XL

## ROS API

You can find ROS API and detailed package description in [ROS_API.md](./ROS_API.md).

## Prepare environment

1. **Create workspace folder and clone `rosbot_xl_ros` repository.**

    ```bash
    mkdir -p ros2_ws/src
    cd ros2_ws
    https://github.com/Combuster54/rosbot_xl_sim src/
    ```
## Build and run Gazebo Harmonic simulation

2. **Build the package**

    ```bash
    export HUSARION_ROS_BUILD=simulation
    source /opt/ros/$ROS_DISTRO/setup.bash

    rosdep init
    rosdep update --rosdistro $ROS_DISTRO
    rosdep install -i --from-path src --rosdistro $ROS_DISTRO -y
    colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
    ```

2. **Running**

    ```bash
    source install/setup.bash
    ros2 launch rosbot_xl_gazebo simulation.launch.py
    ```
