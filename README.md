# waypoints_generator_csv

**This package provides scripts to generate waypoints.**

## Requirement
+ Ubuntu 18.04
+ ROS (Melodic)
+ Python 2.7.x

## Set Up
1. Download waypoints_generator_csv package.

```shell
$ cd ~/catkin_ws/src/
$ git clone https://github.com/HHorimoto/waypoints_generator_csv.git
$ cd ~/catkin_ws
$ catkin_make
```

2. Download necessary package for this package.

```shell
$ sudo apt-get install python-blessed # for key click
```

## How to Use
The package provides three methods for generating waypoints, which can be selected via parameters in the launch file.

```shell
$ roslaunch waypoints_generator_csv waypoints_generator_csv.launch
```

The package also provides a script that just displays the generated waypoints in rviz. after you launch this, select the `Marker` topic from the `add` button in rviz.

```shell
$ roslaunch waypoints_generator_csv publish_marker.launch
```

### Parameters

+ ***select*** : Which method generates waypoints. `key_click(k)` or `clicked_point(c)` or `threshold(t)`.
    default : `threshold`

+ ***file_name*** : Name of the file that contains the waypoints to be generated.
    default : `waypoints`

+ ***dist_th*** : Distance interval of waypoints for `threshold(t)`.
    default : `7.0 [m]`

+ ***theta_th*** : Degree interval of waypoints for `threshold(t)`.
    default : `60.0 [deg]`

+ ***use_debug_marker*** : Display waypoints saved in rviz or not.
    default : `true`

+ ***distance_tolerance*** : Radius of Marker circle
    default : `1.0 [m]`

## Details Of Scripts

### key_click_csv - key_click(k) -
when you press `Enter` key on the keyboard, this script saves the current robot position as a waypoint.
#### Demo video (In Preparation)

### clicked_point_csv - clicked_point(c) -
when you press `Publish Point` button in rviz, the position will be saved as a waypoint.
#### Demo video (In Preparation)

### threshold_csv - threshold(t) -
When the set distance and angle thresholds are exceeded, the script automatically saves the position as a waypoint.
#### Demo video (In Preparation)

## TO DO
- [ ] Insert video demonstration of each method