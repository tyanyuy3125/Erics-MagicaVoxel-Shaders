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