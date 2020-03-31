# Eric's MagicaVoxel Shaders
Shaders for MagicaVoxel including Terrain Generator, Advanced Flood System etc.

## Internationalization
- <a href="./i18n/README-sc.md">简体中文</a> - translated by <a href="http://github.com/codingeric">CodingEric</a>, target version: `0.1.0.0`
- <a href="./i18n/README-fr.md">Français</a> - translated by <a href="http://moiscript.weebly.com/magicavoxel.html">Pilou</a> - Authorized reproduce, target version: `0.0.7.0`

## Project Info
* Current version: `0.1.0.1`
* Tested with `MagicaVoxel 0.99.4 for Windows`
* Released under `MIT License`
* Language: `GLSL`

## Installation
Copy the .txt files from the `shader` directory in this project to the `shader` directory of your MagicaVoxel installation.

## Compatibility
>Notice: The compatibility issue in older GLSL versions are thought of as issues.

| Version | Is compatible | Note |
| ------ | :------: | ------ |
| 0.98.2 | √ | No world system supported |
| 0.99 | √ | Cannot show color id in the command panel |
| 0.99.1 | √ | Cannot show color id in the command panel |
| 0.99.2 | √ | |
| 0.99.3 | √ | |
| 0.99.4.2 | √ | |

## Roadmap
* Cloud generator
* Implement more options (turbulence and so on) to the terrain generator.
* Tree randomizer.

## Contribution
Feel free to make a PR as long as you've followed the contributing guidelines.

## Debug
See <a href="https://github.com/CodingEric/Erics-MagicaVoxel-Shaders/issues/2#issuecomment-449905598">this issue</a>.

## Shaders and usages
>**Note** <br> - The parameters with `<>` can be ignored. Mostly, they are set to 0 as default. <br>  - The shaders are not designed for selected areas without specific explanation. <br>  - The documentation of deprecated/unstable shaders can be found in their folders.
### INDEX
* <a href="#tergen">tergen (Terrain Generator)</a>
* <a href="#tergen2">tergen2 (Terrain Generator 2)</a>
* <a href="#cave">cave (3D Noise Generator)</a>
* <a href="#flow">flow (Waterflow Emulator)</a>
* <a href="#flow2">flow2 (A procedural closed-area filler)</a>
* <a href="#project">project (3d object to 2d plane)</a>
* <a href="#lifegame">lifegame (A 2d cellular automaton)</a>
* <a href="#drop">drop</a>
* <a href="#cubefill">cubefill</a>
### tergen
<a href="#index">index</a>
* Usage:
```
xs tergen [seed] [altitude] 
[noise-scale] [voxel-color] <void-voxel-color> <vertical-shifting> <x-shifting> <y-shifting>
```
* Example:
```
xs tergen 19260817 40 90 1 -1 10 -50 -10
xs tergen 19260817 40 90 1
```

>1. Set void-voxel-color to -1 to not remove the original scene.
>2. By using the xyz-shifting of the shader & the new *world* system of MagicaVoxel 0.99.x, you'll be able to create a large terrain map. (fig. 3)
* Image preview:

  <img src="img/tg.png" width="250px"><img src="img/tg1.png" width="250px"><img src="img/tg2.png" width="250px">
### tergen2
<a href="#index">index</a>
* Usage: 
```
xs tergen2 [seed] [altitude] 
[noise-scale] [voxel-color] <void-voxel-color> <vertical-shifting> <x-shifting> <y-shifting>
```
* Example:
```
xs tergen2 19260817 16 70 1 -1 -10 -50 -10
xs tergen2 19260817 16 70 1
```
>Set void-voxel-color to -1 to not remove the original scene.
* Image preview:

  <img src="img/tg2_2.png" width="250px"><img src="img/tg2_1.png" width="250px">
### cave
<a href="#index">index</a>
* Usage:
```
xs cave [seed] [noise-scale] [voxel-color] [void-voxel-color (-1 for not emptying the scene)] [vertical-shifting] [x-shifting] [y-shifting]
```
* Example: 
```
xs cave 19260817 75 1 -1 10 10 10`
xs cave 19260817 75 1 -1
```
>Set void-voxel-color to -1 to not remove the original scene.
* Image preview:

  <img width="250px" src="img/cave.png">
### flow
<a href="#index">index</a>
* Usage: 
```
xs flow [color-index]
```
* Example: 
```
xs flow 1
```
> The voxels with given index are water source, the shader would not automatically create them, you must attach them first.
* Image preview:

  <img src="img/flowShader.png">
### flow2
<a href="#index">index</a>
* Usage: 
```
xs flow2 [color-index]
```
* Example: 
```
xs flow2 1
```
If you're tired of keeping executing this, consider the `-n [num interations]` parameter.
> The voxels with given index are water source, you must attach them first.
* Image preview:

  <img width="250px" src="img/flow2_1.png">
  <img width="250px" src="img/flow2_2.png">

### project
<a href="#index">index</a>
> Supports x-y plane only. (To be fixed)
* Usage: 
```
xs project [height]
```
* Example: 
```
xs project 64
```
* Image preview:

  <img width="250px" src="img/pro.png">
  <img width="250px" src="img/pro1.png">
  <img width="250px" src="img/pro2.gif">
### lifegame
<a href="#index">index</a>
* Usage: 
```
xs lifegame [color-index]
```
* Example: 
```
xs lifegame 1
```
> Designed for x-y plane. Use single color in your scene, or the shader will destroy it. (To be fixed)
* Image preview:

  <img src="img/l1.png" width="250px">
  <img src="img/l2.png" width="250px">
  <img src="img/l3.png" width="250px">
### drop
<a href="#index">index</a>
> This shader simulates the drop process.
* Usage: 
```
xs drop [color-index]
```
* Example: 
```
xs drop 1
```
* Image preview:

  <img src="img/dr1.png" width="120px"><img src="img/dr2.png" width="120px"><img src="img/dr3.png" width="120px"><img src="img/dr4.png" width="120px"><img src="img/dr5.png" width="120px">
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

  <img src="img/cf.png" width="250px">



