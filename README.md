| Distro | Build dev | Release |
| --- | --- | --- |
| ROS 2 Humble (u22.04) | [![Build Status](https://build.ros2.org/job/Hdev__mrpt_ros__ubuntu_jammy_amd64/badge/icon)](https://build.ros2.org/job/Hdev__mrpt_ros__ubuntu_jammy_amd64/) | [![Version](https://img.shields.io/ros/v/humble/mrpt_ros)](https://index.ros.org/search/?term=mrpt_ros) |
| ROS 2 Iron (u22.04) | [![Build Status](https://build.ros2.org/job/Idev__mrpt_ros__ubuntu_jammy_amd64/badge/icon)](https://build.ros2.org/job/Idev__mrpt_ros__ubuntu_jammy_amd64/) | [![Version](https://img.shields.io/ros/v/iron/mrpt_ros)](https://index.ros.org/search/?term=mrpt_ros) |
| ROS 2 Jazzy (u24.04) | [![Build Status](https://build.ros2.org/job/Jdev__mrpt_ros__ubuntu_noble_amd64/badge/icon)](https://build.ros2.org/job/Jdev__mrpt_ros__ubuntu_noble_amd64/) | [![Version](https://img.shields.io/ros/v/jazzy/mrpt_ros)](https://index.ros.org/search/?term=mrpt_ros) |
| ROS 2 Rolling (u24.04) | [![Build Status](https://build.ros2.org/job/Rdev__mrpt_ros__ubuntu_noble_amd64/badge/icon)](https://build.ros2.org/job/Rdev__mrpt_ros__ubuntu_noble_amd64/) | [![Version](https://img.shields.io/ros/v/rolling/mrpt_ros)](https://index.ros.org/search/?term=mrpt_ros) |


# mrpt-ros
Fine-grained ROS packages for MRPT libraries and apps. This repository is a replacement for
the usage of the [upstream MRPT/mrpt](https://github.com/MRPT/mrpt) repo directly as the ROS
package `mrpt2`.

## Mapping between ROS packages <==> MRPT C++ libraries

These are the `<depend>...</depend>` tags you need to include in
your project `package.xml` depending on [what C++ libraries you use](https://docs.mrpt.org/reference/latest/modules.html):

| ROS 2 package name  | Included MRPT libraries |
|---|---|
| `<depend>mrpt_base</depend>`    | mrpt-io, mrpt-serialization, mrpt-random, mrpt-system, mrpt-rtti, mrpt-containers, mrpt-typemeta, mrpt-core, mrpt-random, mrpt-config, mrpt-expr |
| `<depend>mrpt_gui</depend>`    | mrpt-gui |
| `<depend>mrpt_hwdrivers</depend>`    | mrpt-hwdrivers, mrpt-comms |
| `<depend>mrpt_libapps</depend>`    | mrpt-apps |
| `<depend>mrpt_maps</depend>`    | mrpt-maps, mrpt-graphs |
| `<depend>mrpt_math</depend>`    | mrpt-math |
| `<depend>mrpt_nav</depend>`    | mrpt-nav, mrpt-kinematics |
| `<depend>mrpt_obs</depend>`    | mrpt-obs, mrpt-topography |
| `<depend>mrpt_opengl</depend>`    | mrpt-opengl, mrpt-img |
| `<depend>mrpt_poses</depend>`    | mrpt-poses, mrpt-tfest, mrpt-bayes |
| `<depend>mrpt_ros2bridge</depend>`    | mrpt-ros2bridge |
| `<depend>mrpt_slam</depend>`    | mrpt-slam, mrpt-vision |
| `<depend>mrpt_tclap</depend>`    | mrpt-tclap |
| `<depend>mrpt_apps</depend>`    | Executable [applications](https://docs.mrpt.org/reference/latest/applications.html): RawLogViewer, rawlog-edit, rawlog-grabber, SceneViewer3D, etc. |
| `<depend>python_mrpt</depend>`    | [pymrpt wrapper](https://docs.mrpt.org/reference/latest/wrappers.html) |

Keep in mind that including one C++ library automatically includes all its dependencies, so you do not need to list them all:

![mrpt_libs](docs/graph_mrpt_libs.png)

## Usage

Once binary packages are available via `apt install` from ROS build farm,
you can install required packages like:

```bash
sudo apt install ros-${ROS_DISTRO}-mrpt_base  # or any other as needed
```

In the meanwhile, clone this repo and build with colcon as usual:

```bash
cd ~/ros2_ws/src
git clone --recursive https://github.com/MRPT/mrpt_ros.git
```

## Build status matrix

| Package | ROS 2 Humble <br/> BinBuild |  ROS 2 Iron <br/> BinBuild | ROS 2 Jazzy <br/> BinBuild | ROS 2 Rolling <br/> BinBuild |
| --- | --- | --- | --- |--- |
| mrpt_apps | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_apps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_apps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_apps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_apps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_apps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_apps__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_apps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_apps__ubuntu_noble_amd64__binary/) |
| mrpt_base | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_base__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_base__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_base__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_base__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_base__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_base__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_base__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_base__ubuntu_noble_amd64__binary/) |
| mrpt_gui | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_gui__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_gui__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_gui__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_gui__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_gui__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_gui__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_gui__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_gui__ubuntu_noble_amd64__binary/) |
| mrpt_hwdrivers | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_hwdrivers__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_hwdrivers__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_hwdrivers__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_hwdrivers__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_hwdrivers__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_hwdrivers__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_hwdrivers__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_hwdrivers__ubuntu_noble_amd64__binary/) |
| mrpt_libapps | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_libapps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_libapps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_libapps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_libapps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_libapps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_libapps__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_libapps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_libapps__ubuntu_noble_amd64__binary/) |
| mrpt_maps | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_maps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_maps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_maps__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_maps__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_maps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_maps__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_maps__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_maps__ubuntu_noble_amd64__binary/) |
| mrpt_math | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_math__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_math__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_math__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_math__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_math__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_math__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_math__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_math__ubuntu_noble_amd64__binary/) |
| mrpt_nav | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_nav__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_nav__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_nav__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_nav__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_nav__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_nav__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_nav__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_nav__ubuntu_noble_amd64__binary/) |
| mrpt_obs | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_obs__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_obs__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_obs__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_obs__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_obs__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_obs__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_obs__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_obs__ubuntu_noble_amd64__binary/) |
| mrpt_opengl | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_opengl__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_opengl__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_opengl__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_opengl__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_opengl__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_opengl__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_opengl__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_opengl__ubuntu_noble_amd64__binary/) |
| mrpt_poses | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_poses__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_poses__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_poses__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_poses__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_poses__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_poses__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_poses__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_poses__ubuntu_noble_amd64__binary/) |
| mrpt_ros2bridge | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_ros2bridge__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_ros2bridge__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_ros2bridge__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_ros2bridge__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_ros2bridge__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_ros2bridge__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_ros2bridge__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_ros2bridge__ubuntu_noble_amd64__binary/) |
| mrpt_slam | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_slam__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_slam__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_slam__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_slam__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_slam__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_slam__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_slam__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_slam__ubuntu_noble_amd64__binary/) |
| mrpt_tclap | [![Build Status](https://build.ros2.org/job/Hbin_uJ64__mrpt_tclap__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Hbin_uJ64__mrpt_tclap__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Ibin_uJ64__mrpt_tclap__ubuntu_jammy_amd64__binary/badge/icon)](https://build.ros2.org/job/Ibin_uJ64__mrpt_tclap__ubuntu_jammy_amd64__binary/) | [![Build Status](https://build.ros2.org/job/Jbin_uN64__mrpt_tclap__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Jbin_uN64__mrpt_tclap__ubuntu_noble_amd64__binary/) |[![Build Status](https://build.ros2.org/job/Rbin_uN64__mrpt_tclap__ubuntu_noble_amd64__binary/badge/icon)](https://build.ros2.org/job/Rbin_uN64__mrpt_tclap__ubuntu_noble_amd64__binary/) |


## Motivation for the change
- Faster build times (for each individual package). It was common to see ROS build farms to time out.
- Finer grained dependencies: ROS users can now specify in their `<depend>` tags a part of MRPT only, not the whole thing.

So, **the ROS package `mrpt2` is obsolete now (Jul, 2024)**.

## License
BSD-3
