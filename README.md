# Eric's MagicaVoxel Shaders Collection
Shaders for MagicaVoxel including Terrain Generator, Flood System etc.

## 0x0 Project Info
* Current version: `0.0.2.1`
* Tested with MagicaVoxel 0.98.2 (Beta) for Windows
* Released under GNU GPL v3
* Language: `C\C++` ..ish

## 0x1 Installation
Just copy the .txt files from the `shader` directory in this project into the `shader` directory of your MagicaVoxel installation.

## 0x2 Shaders and usages
### PERLIN NOISE TERRAIN GENERATOR
* File name: `tergen.txt`
* Command-line usage: `xs tergen [seed] [altitude] 
[noise-scale] [voxel-color] [void-voxel-color]`
* Command-line e.g.: `xs tergen 1248343 50 20 1 0`
>1. It is recommended that you set the scene size to 126x126x126 for the best view.
>2. This shader will empty your scene.
* Image preview:

  <img src="img/tg.png" width="250px"></img><img src="img/tg1.png" width="250px"></img>
### DARKER
* File name: `darker.txt`
* Command-line usage: `xs darker`
>1. This shader requires you to set the palette id to 0.
>2. This shader is not designed for selected areas. (This may be improved in the future releases)
* Image preview:

  <img src="img/d.png" width="150px"></img><img src="img/d1.png" width="150px"></img><img src="img/d2.png" width="150px"></img>
### FLOOD
* File name: `flood.txt`
* Command-line usage: `xs flood [height] [color]`
* Command-line e.g.: `xs flood 60 169`
>This shader is not designed for selected areas. (This may be improved in the future releases)
* Image preview:

  <img src="img/f.png" width="250px"></img>
### CUBE FILL
* File name: `cubefill.txt`
* Command-line usages:
  1. `xs cubefill [point1_X] [point1_Y] [point1_Z] [point2_X] [point2_Y] [point2_Z] [voxel color]`
  2. `xs cubefill [pointX] [pointY] [pointZ] [length of a side] [voxel color]`
* Command-line e.g.:
  1. `xs cubefill 1 1 1 7 2 2 216` - Fill a red cuboid between the coordinates (1,1,1) and (7,2,2).
  2. `xs cubefill 50 50 50 10 216` - Take coordinates (50,50,50) as the center, create a red cube with a side length of 10 units.
>This shader will not empty your scene.


