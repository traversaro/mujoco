# MuJoCo Physics

**MuJoCo** stands for **Mu**lti-**Jo**int dynamics with **Co**ntact. It is a
general purpose physics engine that aims to facilitate research and development
in robotics, biomechanics, graphics and animation, machine learning, and other
areas which demand fast and accurate simulation of articulated structures
interacting with their environment.

DeepMind has acquired MuJoCo, and we are currently making preparations to open
source the codebase. In the meantime, MuJoCo is available for download as a free
and unrestricted precompiled binary under the Apache 2.0 license from
the [GitHub Releases page](https://github.com/deepmind/mujoco/releases).

MuJoCo's source code will be released through this GitHub repository once it is
ready. In the meantime, the repository hosts MuJoCo's documentation, C header
files for its public API, sample program code, along with the full source code
for the Python bindings and Unity plugin. If you wish to report bugs or make
feature requests, please file them as [GitHub Issues]. You are also welcome to
send us pull requests to improve anything that has been released into this
repository.


## Overview

MuJoCo is a compiled library with a C API, intended for researchers and
developers. The runtime simulation module is tuned to maximize performance and
operates on low-level data structures which are preallocated by the built-in XML
parser and compiler. The user defines models in the native MJCF scene
description language -- an XML file format designed to be as human readable and
editable as possible. URDF model files can also be loaded. The library includes
interactive visualization with a native GUI, rendered in OpenGL. MuJoCo further
exposes a large number of utility functions for computing physics-related
quantities, not necessarily in a simulation loop. Features include

-   Simulation in generalized coordinates, avoiding joint violations.

-   Inverse dynamics that are well-defined even in the presence of contacts.

-   Unified continuous-time formulation of constraints via convex optimization.

-   Constraints include soft contacts, limits, dry friction, equality
    constraints.

-   Simulation of particle systems, cloth, rope and soft objects.

-   Actuators including motors, cylinders, muscles, tendons, slider-cranks.

-   Choice of Newton, Conjugate Gradient, or Projected Gauss-Seidel solvers.

-   Choice of pyramidal or elliptic friction cones, dense or sparse Jacobians.

-   Choice of Euler or Runge-Kutta numerical integrators.

-   Multi-threaded sampling and finite-difference approximations.

-   Intuitive XML model format (called MJCF) and built-in model compiler.

-   Cross-platform GUI with interactive 3D visualization in OpenGL.

-   Run-time module written in ANSI C and hand-tuned for performance.

[Python bindings](https://github.com/deepmind/mujoco/tree/main/python) and a
[plugin for the Unity game engine](https://github.com/deepmind/mujoco/tree/main/unity)
are also provided and are actively supported by the MuJoCo development team.


## Requirements

MuJoCo binaries are currently built for Linux (x86-64 and AArch64),
Windows (x86-64 only), and macOS. If you require a build for a different
platform, please let us know via [GitHub Issues] or
[Discussions](https://github.com/deepmind/mujoco/discussions).


## Documentation

MuJoCo's current documentation is available at [mujoco.readthedocs.io], which is
serving Sphinx-based webpages derived from the ReStructuredText
[documentation source files].

## Getting Started

There are two easy ways to get started with MuJoCo:

1. **Run `simulate` on your machine.**
[This video](https://www.youtube.com/watch?v=0ORsj_E17B0) shows a
screen capture of `simulate`, MuJoCo's native interactive viewer.
Follow the steps described in the
[Getting Started](https://mujoco.readthedocs.io/en/latest/programming.html#getting-started)
section of the documentation to get `simulate` running locally on your machine.

2. **Explore our online IPython notebooks.**
If you are a Python user, you might want to start with our tutorial notebooks,
running on Google Colab:

  - The first tutorial focuses on the basic MuJoco Python bindings:[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/deepmind/dm_control/blob/main/dm_control/mujoco/tutorial.ipynb).

  - The second tutorial includes more examples of `dm_control`-specific functionality: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/deepmind/dm_control/blob/main/tutorial.ipynb).

## Building from source

Please consult [this section](https://mujoco.readthedocs.io/en/latest/programming.html#building-mujoco-from-source)
in MuJoCo's documentation for general instructions on how to build MuJoCo from
source.

## Citation

If you use MuJoCo for published research, please cite:

```
@inproceedings{todorov2012mujoco,
  title={Mujoco: A physics engine for model-based control},
  author={Todorov, Emanuel and Erez, Tom and Tassa, Yuval},
  booktitle={2012 IEEE/RSJ International Conference on Intelligent Robots and Systems},
  pages={5026--5033},
  year={2012},
  organization={IEEE}
}
```


## License and Disclaimer

Copyright 2021 DeepMind Technologies Limited.

Box collision code ([`engine_collision_box.c`](https://github.com/deepmind/mujoco/tree/main/src/engine/engine_collision_box.c))
is Copyright 2016 Svetoslav Kolev.

ReStructuredText documents, images, and videos in the `doc` directory are made
available under the terms of the Creative Commons Attribution 4.0 (CC BY 4.0)
license. You may obtain a copy of the License at
https://creativecommons.org/licenses/by/4.0/legalcode.

Source code is licensed under the Apache License, Version 2.0. You may obtain a
copy of the License at https://www.apache.org/licenses/LICENSE-2.0.

This is not an officially supported Google product.


[GitHub Issues]: https://github.com/deepmind/mujoco/issues
[documentation source files]: https://github.com/deepmind/mujoco/tree/main/doc
[mujoco.readthedocs.io]: https://mujoco.readthedocs.io
