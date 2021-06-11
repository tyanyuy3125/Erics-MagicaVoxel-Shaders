### FLOOD

* File name: `flood.txt`
* Command-line usage: `xs flood [height] [color]`
* Command-line e.g.: `xs flood 60 169`
>
* Image preview:

  <img src="../img/f.png" width="250px">
### DARKER

* File name: `darker.txt`
* Command-line usage: `xs darker`
> This shader requires you to set the palette id to 0. 
* Image preview:

  <img src="../img/d.png" width="150px"><img src="../img/d1.png" width="150px"><img src="../img/d2.png" width="150px">
### BLANKET
* File name: `blanket.txt`
* Command-line usages: 
  `xs blanket [voxel-color] <noise-seed> <noise-scale> <threshold (0~2 recommend)>`
* Command-line e.g.: `xs blanket 1 1248343 20 1.4`
* Minimal edition e.g.: `xs blanket 1`
>1. The shader will only cover the areas that are not covered. (Like snow)
>2. Esp. if both Terrain Generator & Blanket Shader have the same noise seed as well as scale, and the xyz-shifting of the Terrain Generator is zero, the result of the two shaders mixed together will be like realistic snow cover of high mountains. (fig. 3)
* Image preview:

  <img src="../img/b.png" width="250px">
  <img src="../img/b1.png" width="250px">
  <img src="../img/b2.png" width="250px">
### cubefill
<a href="#index">index</a>
* Usage:
  
  1. 
  ```
  xs cubefill [mode (0 for filling, 1 for frame)] [point1_X] [point1_Y] [point1_Z] [point2_X] [point2_Y] [point2_Z] [voxel color]
  ```

  2. 
  ```
  xs cubefill [mode (0 for filling, 1 for frame)] [pointX] [pointY] [pointZ] [length of a side] [voxel color]
  ```
* Example:
  
  1. 
  
  ```
  xs cubefill 1 1 1 1 7 2 2 216
  ```
  Draw the edge frame of a red cuboid between the coordinates (1,1,1) and (7,2,2).

  2. 
  
  ```
  xs cubefill 0 50 50 50 10 216
  ```
  Take coordinates (50,50,50) as the center, create a red cube with a side length of 10 units.
* Image preview:

  <img src="../img/cf.png" width="250px">
