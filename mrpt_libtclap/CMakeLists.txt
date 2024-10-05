# ROS wrapper CMake project for these MRPT libraries:
#mrpt-tclap

cmake_minimum_required(VERSION 3.5)
project(mrpt_libtclap)

include(ExternalProject)

#----
# Extract version from package.xml
# Example line:" <version>0.3.2</version>"
if(EXISTS ${CMAKE_CURRENT_LIST_DIR}/../override_mrpt_version.cmake)
  include(${CMAKE_CURRENT_LIST_DIR}/../override_mrpt_version.cmake REQUIRED)
endif()
if(NOT MRPT_VERSION_TO_DOWNLOAD)
  file(READ package.xml contentPackageXML)
  string(REGEX MATCH "<version>([0-9\.]*)</version>" _ ${contentPackageXML})
  set(MRPT_VERSION_TO_DOWNLOAD ${CMAKE_MATCH_1})
  set(_VERSION_SRC "(detected in package.xml)")
else()
set(_VERSION_SRC "(***OVERRIDEN VERSION***)")
endif()
message(STATUS "MRPT_VERSION_TO_DOWNLOAD: ${MRPT_VERSION_TO_DOWNLOAD} ${_VERSION_SRC}")
#----


# For local builds, avoid the waste of time and disk of cloning mrpt within each package,
# which makes sense only in build farms:
# --------------------------------------------------------------------------------------------
if (EXISTS ${CMAKE_BINARY_DIR}/../mrpt_libbase/mrpt-build/src/mrpt/CMakeLists.txt AND NOT "$ENV{HOME}" STREQUAL "/home/buildfarm")
  # reuse existing cloned version:
  set(src_cmds
    SOURCE_DIR ${CMAKE_BINARY_DIR}/../mrpt_libbase/mrpt-build/src/mrpt/
  )
else()
  # Default: clone from github:
  set(src_cmds
    GIT_REPOSITORY https://github.com/MRPT/mrpt.git
    GIT_TAG ${MRPT_VERSION_TO_DOWNLOAD}
  )
endif()

# EP:
# -------------------------------
ExternalProject_Add(
  mrpt
  PREFIX ${CMAKE_BINARY_DIR}/mrpt-build
  ${src_cmds}
  CMAKE_ARGS
    # Main settings:
    -DCMAKE_INSTALL_PREFIX=${CMAKE_INSTALL_PREFIX}
    -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}
    # Disabled stuff:
    -DDISABLE_JSONCPP=ON
    -DMRPT_INSTALL_EXAMPLES=OFF
    -DMRPT_INSTALL_SHARE_DIRS=OFF
    -DMRPT_BUILD_MANPAGES=OFF
    -DDISABLE_ROS=ON # save cmake configure time
    # Granular builds for each ROS package:
    -DMRPT_BUILD_APPLICATIONS=OFF
    -DMRPT_DISABLE_PYTHON_BINDINGS=ON
    -DMRPT_WITH_ROBOPEAK_LIDAR=OFF
    -DMRPT_BUILD_wxThings=OFF
    -DMRPT_BUILD_rplidar_sdk=OFF
    -DMRPT_BUILD_xsens=OFF
    -DMRPT_BUILD_nanogui=OFF
    -DMRPT_INSTALL_CONFIG_HEADERS=OFF
    -DMRPT_INSTALL_EMBEDDED_nanoflann=OFF
    # Libs:
    -DBUILD_mrpt-apps=OFF
    -DBUILD_mrpt-bayes=OFF
    -DBUILD_mrpt-comms=OFF
    -DBUILD_mrpt-config=OFF
    -DBUILD_mrpt-containers=OFF
    -DBUILD_mrpt-core=OFF
    -DBUILD_mrpt-expr=OFF
    -DBUILD_mrpt-graphs=OFF
    -DBUILD_mrpt-graphslam=OFF
    -DBUILD_mrpt-gui=OFF
    -DBUILD_mrpt-hwdrivers=OFF
    -DBUILD_mrpt-img=OFF
    -DBUILD_mrpt-io=OFF
    -DBUILD_mrpt-kinematics=OFF
    -DBUILD_mrpt-maps=OFF
    -DBUILD_mrpt-math=OFF
    -DBUILD_mrpt-nav=OFF
    -DBUILD_mrpt-obs=OFF
    -DBUILD_mrpt-opengl=OFF
    -DBUILD_mrpt-poses=OFF
    -DBUILD_mrpt-random=OFF
#    -DBUILD_mrpt-ros$ENV{ROS_VERSION}bridge=OFF     # ROS1 or ROS2
    -DBUILD_mrpt-rtti=OFF
    -DBUILD_mrpt-serialization=OFF
    -DBUILD_mrpt-slam=OFF
    -DBUILD_mrpt-system=OFF
    -DBUILD_mrpt-tclap=ON
    -DBUILD_mrpt-tfest=OFF
    -DBUILD_mrpt-topography=OFF
    -DBUILD_mrpt-typemeta=OFF
    -DBUILD_mrpt-vision=OFF
  # no install during build
  INSTALL_COMMAND ""
)

# Actual "install":
install(CODE "execute_process(COMMAND ${CMAKE_COMMAND} --build ${CMAKE_BINARY_DIR}/mrpt-build/src/mrpt-build --target install)")
