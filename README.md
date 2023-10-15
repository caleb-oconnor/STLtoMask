# STLtoMask

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Label JSON](#label-json)

  
## Overview

Create a 3D image based off of an STL file and user defined spacing. Additional, options exist for rotating the mesh, adding a 3MF file to create a "color-intensity" on the surface of the image, and flipping the iamge and mesh along the vertical axial plane.

## Features

Converts STL file to a 3D image.

Options:
  - Add 3MF file to transfer mesh color to surface insensity on the image.
  - Allows mesh rotation before image creation.
  - Flip image/mesh before output along the vertical axis in the axial plane.


## Installation
Using [pip](https://pip.pypa.io/en/stable/):
```
pip install StlMaskConverter
```

## Usage
To run the module, use the following command:

```bash
usage: converter.py [-h] -i INPUT -o OUTPUT -s SPACING [SPACING ...] [-m THREE_MF] [-r ROTATION [ROTATION ...]] [-f]


optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        STL file
  -o OUTPUT, --output OUTPUT
                        Directory to output mask and STL if edited
  -s SPACING [SPACING ...], --spacing SPACING [SPACING ...]
                        Output mask spacing in mm example [1, 1, 1]
  -m THREE_MF, --three_mf THREE_MF
                        3mf file needed for adding intensity to mask
  -r ROTATION [ROTATION ...], --rotation ROTATION [ROTATION ...]
                        Rotation in dictionary form indicating order ex: {yxz: [10, 30, 0}, meaning rotate y=10 degrees then x=30 degrees
  -f, --flip            Flips axial plane along the vertical line

```
