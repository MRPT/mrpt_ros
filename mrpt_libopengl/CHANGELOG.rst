^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package mrpt_libopengl
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

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
