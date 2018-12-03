# Eric's MagicaVoxel Shaders
Shaders for MagicaVoxel including Terrain Generator, Advanced Flood System etc.

## Internationalization
- <a href="./i18n/README-sc.md">简体中文</a> - translated by <a href="http://github.com/codingeric">CodingEric</a>
- <a href="./i18n/README-fr.md">Français</a> - translated by <a href="http://moiscript.weebly.com/magicavoxel.html">Pilou</a> - Authorized reproduce

## Project Info
* Current version: `0.0.7.0`
* State: `LTS`
* Tested with `MagicaVoxel 0.99.2 for Windows`
* Released under `MIT License`
* Language: `GLSL`

## Installation
Copy the .txt files from the `shader` directory in this project to the `shader` directory of your MagicaVoxel installation.

## Compatibility
>Notice: The compatibility issue in older GLSL versions will be think of as bugs, please post them in the issues of the project.

| Version | Is compatible | Note |
| ------ | :------: | ------ |
| 0.98.2 | √ | No world system supported |
| 0.99 | √ | |
| 0.99.1 | √ | |
| 0.99.2 | √ | |

## Shaders and usages
>Note: The parameters with `<>` can be ignored. Mostly, they are set to 0 as default.
### INDEX
* <a href="#terrain-generator">Terrain generator</a>
* <a href="#flow">Flow</a>
* <a href="#flow2">Flow2</a>
* <a href="#hyperflood">[Unstable] Hyperflood</a>
* <a href="#life-game">Life game</a>
* <a href="#blanket">Blanket</a>
* <a href="#cube-filling">Cube filling</a>
* <a href="#flood">Flood</a>
* <a href="#darker">Darker</a>
### TERRAIN GENERATOR
<a href="#index">back to index</a>
* File name: `tergen.txt`
* Command-line usage: `xs tergen [seed] [altitude] 
[noise-scale] [voxel-color] <void-voxel-color> <vertical-shifting> <x-shifting> <y-shifting>`
* Command-line e.g.: `xs tergen 19260817 50 20 1 0 -10 10 10`
* Minimal edition e.g.: `xs tergen 19260817 50 20 1`
>1. It is recommended that you set the scene size to 126x126x126 for the best view.
>2. ~~This shader will empty your scene.~~ Set void-voxel-color to -1 to not remove the original scene.
>3. By using the xyz-shifting of the shader & the new *world* system of MagicaVoxel 0.99.x, you'll be able to create a large terrain map. (fig. 3)
* Image preview:

  <img src="img/tg.png" width="250px"></img><img src="img/tg1.png" width="250px"></img>
  <img src="img/tg2.png" width="250px"></img>
### FLOW
<a href="#index">back to index</a>
> This shader emulates the waterflow mechanics in the nature.
* File name: `flow.txt`
* Command-line usage: `xs flow [color-index]`
* Command-line e.g.: `xs flow 1`
> The voxels with given index are water source, the shader would not automatically create them, you must attach them first.
* Image preview:

  <img src="img/flowShader.png"></img>
### FLOW2
<a href="#index">back to index</a>
> In fact, it's a replacement of the unstable `hyperflood` shader.<br/>In the fig.2 of preview section, you can see the shader does provide a solution for the closed areas.
* File name: `flow2.txt`
* Command-line usage: `xs flow2 [color-index]`
* Command-line e.g.: `xs flow2 1`
> The voxels with given index are water source, the shader would not automatically create them, you must attach them first.
* Image preview:

  <img width="250px" src="img/flow2_1.png"></img>
  <img width="250px" src="img/flow2_2.png"></img>
### HYPERFLOOD
<a href="#index">back to index</a>
>**UNSTABLE. DO NOT USE.<br>GO TO FLOW2 INSTEAD.**

>Unlike the classic flood shader, this shader provides a solution for closed water area.
* File name: `hyperflood.txt`
* Command-line usage: `xs hyperflood [x] [y] [z]` (The parameters represent the coordinate of the water source.)
* Command-line e.g.: `xs hyperflood 3 5 3`
>1. The color of water is controlled by selected color in the palette.
>2. DANGER - READ BEFORE USE
<br>- THE SHADER ONLY SUPPORTS SCENES WITH LESS THAN 40 UNITS OF XYZ-VOLUMESIZE. (You can change line 17 to remove the limit, but think over first.)
<br>- LIMITED BY THE INNER EXPLAINATOR OF MAGICAVOXEL, THE SHADER IS NOT STABLE. IF THE FILLING SPACE IS TOO LARGE, MAGICAVOXEL MAY CRASH.
* Image preview:

  <img src="img/h.png"></img>
### LIFE GAME
<a href="#index">back to index</a>
* File name: `lifegame.txt`
* Command-line usage: `xs lifegame [color-index]`
* Command-line e.g.: `xs lifegame 1`
> Designed for x-y plane. Use single color in your scene, or the shader will destroy it.
* Image preview:

  <img src="img/l1.png" width="250px"></img>
  <img src="img/l2.png" width="250px"></img>
  <img src="img/l3.png" width="250px"></img>
### BLANKET
<a href="#index">back to index</a>
* File name: `blanket.txt`
* Command-line usages: 
  `xs blanket [voxel-color] <noise-seed> <noise-scale> <threshold (0~2 recommend)>`
* Command-line e.g.: `xs blanket 1 1248343 20 1.4`
* Minimal edition e.g.: `xs blanket 1`
>1. The shader will only cover the areas that are not covered. (Like snow)
>2. Esp. if both Terrain Generator & Blanket Shader have the same noise seed as well as scale, and the xyz-shifting of the Terrain Generator is zero, the result of the two shaders mixed together will be like realistic snow cover of high mountains. (fig. 3)
* Image preview:

  <img src="img/b.png" width="250px"></img>
  <img src="img/b1.png" width="250px"></img>
  <img src="img/b2.png" width="250px"></img>
### CUBE FILLING
<a href="#index">back to index</a>
* File name: `cubefill.txt`
* Command-line usages:
  1. `xs cubefill [mode (0 for filling, 1 for frame)] [point1_X] [point1_Y] [point1_Z] [point2_X] [point2_Y] [point2_Z] [voxel color]`
  2. `xs cubefill [mode (0 for filling, 1 for frame)] [pointX] [pointY] [pointZ] [length of a side] [voxel color]`
* Command-line e.g.:
  1. `xs cubefill 1 1 1 1 7 2 2 216` - Draw the edge frame of a red cuboid between the coordinates (1,1,1) and (7,2,2).
  2. `xs cubefill 0 50 50 50 10 216` - Take coordinates (50,50,50) as the center, create a red cube with a side length of 10 units.
* Image preview:

  <img src="img/cf.png" width="250px"></img>
>This shader will not empty your scene.
### FLOOD
<a href="#index">back to index</a>
* File name: `flood.txt`
* Command-line usage: `xs flood [height] [color]`
* Command-line e.g.: `xs flood 60 169`
>This shader is not designed for selected areas. 
* Image preview:

  <img src="img/f.png" width="250px"></img>
### DARKER
<a href="#index">back to index</a>
* File name: `darker.txt`
* Command-line usage: `xs darker`
>1. This shader requires you to set the palette id to 0.
>2. This shader is not designed for selected areas. 
* Image preview:

  <img src="img/d.png" width="150px"></img><img src="img/d1.png" width="150px"></img><img src="img/d2.png" width="150px"></img>


