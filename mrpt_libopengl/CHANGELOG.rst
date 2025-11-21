^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_libopengl
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Forthcoming
-----------

2.15.1 (2025-10-29)
-------------------
* Remove obsolete BUILD_ros2bridge cmake variable
* Add missing opencv dependency after removal of cv_bridge
* Contributors: Jose Luis Blanco-Claraco

2.15.0 (2025-10-26)
-------------------
* Remove deps on ROS message packages, following the removal of mrpt-ros bridge into its own repository
* Contributors: Jose Luis Blanco-Claraco

2.14.16 (2025-10-15)
--------------------
* Fix mrpt::opengl::CPointCloudColoured throwing if the source cloud map may have color and color/intensity channels are actually empty.

2.14.15 (2025-09-29)
--------------------
* Fix regressions from former release.

2.14.14 (2025-09-27)
--------------------
* Fixed opengl unit tests against crashes under some build flags.
* Fix mrpt::opengl::CEllipsoid3D wrong direction.

2.14.12 (2025-08-31)
--------------------
* New method mrpt::opengl::CPointCloudColoured::setAllPointsAlpha().

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
* mrpt::opengl::Texture now caches "texture names" (OpenGL texture IDs) via image data, boosting performance of MVSim boot up time.

2.14.5 (2024-11-05)
-------------------

2.14.4 (2024-10-19)
-------------------

2.14.3 (2024-10-12)
-------------------
* mrpt::img::CImage::rotateImage(): Special angles 90,-90, 180 are handled as expected with a quick image transformation and rotation.

2.14.2 (2024-10-05)
-------------------
* Add support for override_mrpt_version for local builds
* mrpt::opengl::CMesh: Remove the annoying warning "Texture image and Z matrix have different sizes"
* Contributors: Jose Luis Blanco-Claraco

2.14.1 (2024-09-24)
-------------------
* New method mrpt::opengl::CAssimpModel::split_triangles_rendering_bbox() to enable a new feature in Assimp 3D models: splitting into smaller triangle sets for correct z-ordering of semitransparent objects; e.g. required for trees with masked leaves.
* SkyBox shader changed its internal ID so it gets rendered before potentially transparent elements, fixing render artifacts.
* mrpt::opengl::Texture: Wrapped OpenGL options for texture coordinate wrapping.

2.13.7 (2024-08-23)
-------------------

2.13.6 (2024-08-14)
-------------------
* Add lib suffix to package names
* Contributors: Jose Luis Blanco-Claraco
