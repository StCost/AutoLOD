# Outdated Updated AutoLOD
# Prefer another maintained [fork](https://github.com/YvesAlbuquerque/AutoLOD)
# or use unity 6 and GPU occlusion + mesh simplifier

Automatic LOD generation + scene optimization - [Initial release](https://github.com/Unity-Technologies/AutoLOD) was on January 12, 2018 via [blogpost](https://blogs.unity3d.com/2018/01/12/unity-labs-autolod-experimenting-with-automatic-performance-improvements/)

AutoLOD is primarily a framework for enabling automatic post-processing of geometrical model assets on import to create simplified levels-of-detail (LOD). A [default mesh simplifier](https://github.com/Whinarn/UnityMeshSimplifier/) is included, but can be swapped out with other simplifiers and on a per-model basis if needed. Additionally, a whole scene can be hierarchically chunked into LODs with [SceneLOD](https://github.com/Unity-Technologies/AutoLOD/wiki/Scenelod).

## Evaluating
Required Unity Editor Version
- Recommended [Unity 2021.1](https://unity.com/releases/editor/whats-new/2021.1.0) or later
- Minimum Unity 2018.4 (LTS) ([original release](https://github.com/Unity-Technologies/AutoLOD) was on 2018.1)
- Last tested with [Unity 2023.3.0b4](https://unity.com/releases/editor/beta/2023.3.0b4)

## Experimental Status
It’s important to note that AutoLOD is an experimental feature. As such, there is no formal support (e.g. FogBugz, support@unity3d.com, Premium Support, etc.) offered, so please do not use these channels. Instead, post your questions, comments, suggestions, and issues here on GitHub.

**As with anything experimental/preview/alpha/beta, it is always a good idea to make a backup of your project before using.**

Experimental means this:
- Namespaces, classes, software architecture, prefabs, etc. can change at any point. If you are writing your own tools, then you might need to update them as these things change.
- There won’t always be an upgrade path from one release to the next, so you might need to fix things manually, which leads to the next point...
- Stuff can and will break (!)
- There’s **no guarantee** that this project will move out of experimental status within any specific timeframe.
- As such, there is no guarantee that this will remain an actively supported project.

## Features
- LOD generation on model import with sensible [defaults](https://github.com/Unity-Technologies/AutoLOD/wiki/Home)
- Project-wide and per-model LOD import settings
- Asynchronous, pluggable LOD generation framework with built-in support for:
  - [UnityMeshSimplifier](https://github.com/Whinarn/UnityMeshSimplifier/)
  - [Simplygon](https://simplygon.com/)
  - [InstaLOD](https://instalod.com/)
- Hierarchical LOD support via [SceneLOD](https://github.com/Unity-Technologies/AutoLOD/wiki/Scenelod) -> [watch a [quick tutorial video](http://www.youtube.com/watch?v=EuBeZvzVwrw "SceneLOD Tutorial")]

### Useful classes (for your own projects, too!)
- [MonoBehaviourHelper](Scripts/Helpers/MonoBehaviourHelper.cs) - a way to run coroutines in the editor + main thread execution from worker threads
- [LODGroupExtensions](Scripts/Extensions/LODGroupExtensions.cs) - useful extension methods (e.g. GetCurrentLOD)
- [TimedEnumerator](Scripts/Helpers/TimedEnumerator.cs) -  a way to control maximum execution time of coroutines
- [TextureAtlasModule](Scripts/Editor/TextureAtlasModule.cs) - automatically generate texture atlases
- [WorkingMesh](Scripts/Helpers/WorkingMesh.cs) - a thread-safe mesh (_and now job-friendly!_) struct

### Cloning locally to your project (requires [git-lfs](https://git-lfs.github.com/))
1. Create a new Unity project or use an existing one
2. From the command line change directory to your project's `Packages` directory.
3. Run `git lfs clone https://github.com/StCost/AutoLOD`

### Download as ZIP / Manual Install
1. Visit GitHub's [AutoLOD](https://github.com/StCost/AutoLOD) repository
2. Click the green `Code` button and select `Download ZIP`
3. Extract the contents of the ZIP file into your project
