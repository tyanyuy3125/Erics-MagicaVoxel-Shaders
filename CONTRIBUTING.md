# Contributing guidelines
## APIs
The shaders should be written in GL Shading Language. It supports most of C language functions.

 | Name | Type | Description | Post script |
 | - | - | - | - |
 | iVolumeSize | vec3 | volume size [1-126] | |
 | iColorIndex | float | current color index [1-255] | |
 | iMirror | vec3 | current mirror mode [0-1] | |
 | iAxis | vec3 | current axis mode [0-1] | |
 | iFrame | float | current anim frame index | Deprecated (v0.99+) |
 | iNumFrames | float | total num of anim frames | Deprecated (v0.99+) |
 | iIter | float | current iteration index | Not working (v0.99.1) |
 | iRand | vec4 | random number | |
 | iArgs[8] | float | user args | |
 | voxel(vec3 v) | float | get voxel color index at position v | |
 ## EDITING GUIDES
 * The shader's format should be txt, which is used by most of GLSL shaders.
 * Your code should begin like this: 
```
/*
Via Github@[Your name]
If you like this project, give it a star!
GL Shading Language.
[Shader name] for Magicavoxel
Command-line usage: '[Usage template]' ([Other comments here])
e.g. [Usage example]
[Post script]
MIT License
*/
```
 * Use functions often
 * Don't name the variable with the only single characters **without a specific meaning** (like `a`, `bbb`, `___` etc).
 * Move the shader file to `unstable` directory if you think your shader needs optimization.
 * Don't forget to add the related description of your shader to `README.md`, the original file may be the example for you.
 ## CHECK-IN
 Summary only, no description. No punctuation needed.
