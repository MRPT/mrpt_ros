^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_apps
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.14.7 (2024-12-09)
-------------------
* rosbag2rawlog (ROS1): Implement conversion of NavSatFix -> mrpt::obs::CObservationGPS

2.14.5 (2024-11-05)
-------------------
* GridmapNavSimul: Loading a different gridmap won't update the map visualization.

2.14.4 (2024-10-19)
-------------------
* package.xml and cmake: Fix generation of rosbag2rawlog for ROS 1 version of package mrpt_apps
* rosbag2rawlog: Fix detection of mrpt-ros1bridge when built within mrpt_ros ROS packaging.
* Contributors: Jose Luis Blanco-Claraco

2.14.3 (2024-10-12)
-------------------

2.14.2 (2024-10-05)
-------------------
* Add support for override_mrpt_version for local builds
* Contributors: Jose Luis Blanco-Claraco

2.14.1 (2024-09-24)
-------------------
* SceneViewer3D: New button to enable shadow casting.

2.13.7 (2024-08-23)
-------------------

2.13.6 (2024-08-14)
-------------------
* Add lib suffix to package names
* Disable ROS detection to save cmake configure time
* more packages
* Contributors: Jose Luis Blanco-Claraco
