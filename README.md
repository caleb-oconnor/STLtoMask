# STLtoMask

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Example](#example)
  - [Basic](#basic)
  - [Advanced](#advanced)
  
## Overview

Create a 3D image based off of an STL file and user defined spacing. Additional, options exist for rotating the mesh, adding a 3MF file to create a "color-intensity" on the surface of the image, and flipping the image and mesh along the vertical axial plane. 

The script produces 2 files: 1) Metaimage file for the image, 2) STL file just incase any rotations/flips were added (makes this file even if nothing was changed from the original STL file).

Notes:
  - The spacing must be integeres, even if floats are input they will be converted.
  - Adding a 3MF file will greatly increase the computation time depending on mesh size ~ 30 minutes for 1 million points.

## Features

Converts STL file to a 3D image.

Options:
  - Add 3MF file to transfer mesh color to surface insensity on the image.
  - Allows mesh rotation before image creation.
  - Flip image/mesh before output along the vertical axis in the axial plane.


## Installation
Using [pip](https://pip.pypa.io/en/stable/):
```
pip install STLtoMask
```

## Examples
### Basic
```python
from STLtoMask.converter import stl_to_mask

input_path = r'/path/to/STL_file'
output_path = r/path/to/export/data'
spacing = [1, 1, 1]

stl_to_mask(input_path, output_path, spacing)

```
### Advanced
```python
from STLtoMask.converter import stl_to_mask

input_path = r'/path/to/STL_file'
output_path = r/path/to/export/data'
spacing = [1, 1, 1]

threemf_path = r'/path/to/3mf_file'
rotation = {'zxy': [10, 5, 20]}

stl_to_mask(input_path, output_path, spacing, three_mf_path, rotation, flip=True)

```
