^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_libnav
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

2.14.4 (2024-10-19)
-------------------
* mrpt::nav::CAbstractPTGBasedReactive: Missing heading information in recently-added TP-Space targets as TPose2D.

2.14.3 (2024-10-12)
-------------------
* mrpt::nav::CWaypointsNavigator: New parameter "minimum_target_approach_per_step" and feature to keep approaching waypoints until no significant improvement is done.
* mrpt::nav::CHolonomicFullEval: Rewritten TP-Space data structures so the target heading is visible to holonomic evaluator algorithms. Added a new weight [7] related to correct alignment at target. All RNAV INI files have been updated accordingly.

2.14.2 (2024-10-05)
-------------------
* Add support for override_mrpt_version for local builds
* Add generic internalState to PTGs.
* Contributors: Jose Luis Blanco-Claraco

2.14.1 (2024-09-24)
-------------------

2.13.7 (2024-08-23)
-------------------

2.13.6 (2024-08-14)
-------------------
* Add lib suffix to package names
* Contributors: Jose Luis Blanco-Claraco
