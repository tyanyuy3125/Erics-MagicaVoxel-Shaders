# Eric's MagicaVoxel Shaders
aka EMVS.

Shaders for MagicaVoxel including Terrain Generator, Advanced Flood System etc.

## Internationalization
- <a href="./i18n/README-sc.md">简体中文</a> - translated by <a href="http://github.com/codingeric">CodingEric</a>, target version: `54`
- <a href="./i18n/README-fr.md">Français</a> - translated by <a href="http://moiscript.weebly.com/magicavoxel.html">Pilou</a> - Authorized reproduce, target version: `0.0.7.0`

## Project Info
* Current version: `54`
* Released under `MIT License`

## Installation
Copy the .txt files from the `shader` directory in this project to the `shader` directory of your MagicaVoxel installation.

## Compatibility

| Version | Is compatible | Note |
| ------ | :------: | ------ |
| 0.99.5 and before | not compatible after EMVS version 54 | |
| 0.99.5.1 and after | all EMVS versions are compatible  | |

## Roadmap

* Cloud generator
* Implement more options (turbulence and so on) to the terrain generator.
* Tree randomizer.

## Debugging

See <a href="https://github.com/CodingEric/Erics-MagicaVoxel-Shaders/issues/2#issuecomment-449905598">this issue</a>.

## Shaders
Starting from version 54, EMVS **no longer** supports command execution. Please configure the relevant parameters through the graphical options provided by MagicaVoxel 0.99.5.1 onwards.

At the same time, for the graphical options are very clear, the explanations of parameters are not provided in this document. 

### Index
* <a href="#tergen">tergen</a>
* <a href="#tergen2">tergen2</a>
* <a href="#cave">cave</a>
* <a href="#flow">flow</a>
* <a href="#flow2">flow2</a>
* <a href="#project">project</a>
* <a href="#gol">gol</a>
* <a href="#drop">drop</a>

### tergen
<a href="#index">index</a>

"tergen" is a 2d noise generator.

* Set Air Color to -1 to retain existing voxels.
* By using the xyz-shifting of the shader & the new *world* system of MagicaVoxel 0.99.x, you'll be able to create a large terrain map. (fig. 3)

<img src="img/tg.png" width="250px"><img src="img/tg1.png" width="250px"><img src="img/tg2.png" width="250px">

### tergen2
<a href="#index">index</a>

"tergen2" is a modified version of "tergen", which creates terrain only above the existing voxels.

Set Air Color to -1 to retain existing voxels.

<img src="img/tg2_2.png" width="250px"><img src="img/tg2_1.png" width="250px"><img src="img/tg2_3.png" width="250px"><img src="img/tg2_4.png" width="250px">

### cave
<a href="#index">index</a>

"cave" is a 3d noise generator.

Set Air Color to -1 to retain existing voxels.

<img width="250px" src="img/cave.png">

### flow
<a href="#index">index</a>

"flow" simulates the downflow of water in nature.

* You may set Iteration value to a certain number to simplify the process.
* The voxels with given index are water source, the shader would not automatically create them, you must attach them first.

<img src="img/flowShader.png">

### flow2
<a href="#index">index</a>

"flow2" is a modified version of "flow", by keep executing it, you can fill an enclosed area well without overflowing to the outside.

* You may set Iteration value to a certain number to simplify the process.
* The voxels with given index are water source, you must attach them first.

<img width="250px" src="img/flow2_1.png">
<img width="250px" src="img/flow2_2.png">

### project
<a href="#index">index</a>

"project" enables you to project a 2d plane onto the surface of 3d objects below it.

<img width="250px" src="img/pro.gif">

### gol
<a href="#index">index</a>

"gol" is the voxel shader for Conway's Game of Life.

The shader is designed for x-y plane. Use single color in your scene, or the shader will destroy it. (To be fixed)

<img src="img/l1.png" width="250px"><img src="img/l2.png" width="250px"><img src="img/l3.png" width="250px">

### drop
<a href="#index">index</a>

"drop" moves the dangling voxel down one unit in a single execution. 

<img src="img/dr1.png" width="120px"><img src="img/dr2.png" width="120px"><img src="img/dr3.png" width="120px"><img src="img/dr4.png" width="120px"><img src="img/dr5.png" width="120px">

