# STLtoMask

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
  - [Example](#example)

  
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

### Example
```bash
python converter.py -i '\stl_filepath' -o 'output_dir' -s 1 1 1 -m '\3mf_filepath' -r xyz 10 20 30.1 -f False

```
