# mrpt-ros
Fine-grained ROS packages for MRPT libraries and apps. This repository is a replacement for
the usage of the [upstream MRPT/mrpt](https://github.com/MRPT/mrpt) repo directly as the ROS
package `mrpt2`.

## Build status matrix
(Add me!)

## Motivation for the change
- Faster build times (for each individual package). It was common to see ROS build farms to time out.
- Finer grained dependencies: ROS users can now specify in their `<depend>` tags a part of MRPT only, not the whole thing.

So, **the ROS package `mrpt2` is obsolete now**.

## License
BSD-3
