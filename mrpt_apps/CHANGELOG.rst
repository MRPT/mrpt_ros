^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_apps
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.15.1 (2025-10-29)
-------------------
* Remove obsolete BUILD_ros2bridge cmake variable
* Add missing opencv dependency after removal of cv_bridge
* Contributors: Jose Luis Blanco-Claraco

2.15.0 (2025-10-26)
-------------------
* Remove deps on ROS message packages, following the removal of mrpt-ros bridge into its own repository
* RawLogViewer:  Show stats for mrpt::maps::CGenericPoinsMap. GUI options to colorize clouds by any point cloud field.
* Contributors: Jose Luis Blanco-Claraco

2.14.16 (2025-10-15)
--------------------

2.14.15 (2025-09-29)
--------------------

2.14.14 (2025-09-27)
--------------------

2.14.13 (2025-09-27)
--------------------

2.14.12 (2025-08-31)
--------------------

2.14.11 (2025-05-31)
--------------------

2.14.10 (2025-05-23)
--------------------

2.14.9 (2025-05-17)
-------------------

2.14.8 (2025-04-25)
-------------------
* Fix RawLogViewer ICP module.

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
