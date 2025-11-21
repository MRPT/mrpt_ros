^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_libmaps
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------
* mrpt::maps::CGenericPointsMap now supports fields of type `double` too.
* Merge pull request `#5 <https://github.com/MRPT/mrpt_ros/issues/5>`_ from wentasah/readd-octomap
  libmaps: Depend on liboctomap-dev
* libmaps: Depend on liboctomap-dev
  Dependency on liboctomap-dev was removed in commit e94c04e ("Remove
  deps on ROS message packages, following the removal of mrpt-ros bridge
  into its own repository", 2025-10-23), but libmaps needs octomap to
  build. Otherwise, the following error message is printed:
  /build/mrpt-build/src/mrpt/libs/maps/src/maps/COctoMap.cpp:18:10:
  fatal error: octomap/OcTree.h: No such file or directory
* Contributors: Jose Luis Blanco-Claraco, Michal Sojka

2.15.1 (2025-10-29)
-------------------
* Remove obsolete BUILD_ros2bridge cmake variable
* Add missing opencv dependency after removal of cv_bridge
* Contributors: Jose Luis Blanco-Claraco

2.15.0 (2025-10-26)
-------------------
* Remove deps on ROS message packages, following the removal of mrpt-ros bridge into its own repository
* Add new mrpt::maps::CGenericPointsMap
* Refactor around mrpt::maps::CPointsMap for more efficient generic insertion of maps in others with arbitrary per-point fields.
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

2.14.7 (2024-12-09)
-------------------

2.14.5 (2024-11-05)
-------------------
* mrpt::maps::CPointsMapXYZIRT::getPointRGB() now handles the case of no intensity without throwing, fixing the visualization of such clouds through mrpt::opengl::CPointCloudColoured::loadFromPointsMap().

2.14.4 (2024-10-19)
-------------------

2.14.3 (2024-10-12)
-------------------

2.14.2 (2024-10-05)
-------------------
* Add support for override_mrpt_version for local builds
* Contributors: Jose Luis Blanco-Claraco

2.14.1 (2024-09-24)
-------------------

2.13.7 (2024-08-23)
-------------------

2.13.6 (2024-08-14)
-------------------
* Add lib suffix to package names
* Contributors: Jose Luis Blanco-Claraco
