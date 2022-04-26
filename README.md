# paraview-build

[![GitHub version](https://badge.fury.io/gh/GRChombo%2Fparaview-build.svg)](https://badge.fury.io/gh/GRChombo%2Fparaview-build)
![Build and release action](https://github.com/GRChombo/paraview-build/actions/workflows/build-and-release.yml/badge.svg)

A repository with a GitHub action to build and package[^1]
[ParaView](https://github.com/Kitware/ParaView) using the
[Superbuild](https://gitlab.kitware.com/paraview/paraview-superbuild) on the
Ubuntu 20.04 GitHub action runners.

The build is/will be used in the GitHub action which tests the [ParaView
Catalyst](https://www.paraview.org/in-situ/) instrumentation in GRChombo. It is
built against the Ubuntu 20.04 system libraries so is unlikely to work on other
Linux distributions with different library/package versions.

The build has the following features:
* Catalyst Rendering edition
* OSMesa rendering
* Python 3 support
* MPI
* LLVM support
* Release build with debugging info

[^1]: Note that as the Superbuild `cpack` targets do not currently include the
paraview-config script which is required for building GRChombo with ParaView
Catalyst in-situ support, the packaging in this action is rudimentary and just
makes a tarball from the relevant build directory. This is another reason why
the builds in this repository are even less likely to be portable.
