Imgui v1.89.5, with cmake support.

## Build:

- If you want to build the base imgui with cmake, just do:

```
cmake . -B ./build
cmake --build ./build
```

- If you also want to build imgui with misc/cpp addon, add -DWITH_STDLIB=ON flag
during buildfile generation step:

```
cmake . -B ./build -DWITH_STDLIB=ON

```

## Using in your own projects:

This fork only feature 3 new files - this readme and two CMakeLists.txt (in
project's root and in misc/cpp). If you want to use these as references for your
own imgui setup - feel free to do so!

## TODO:

- Build support for various backends (since I'm using it with raylib via rlImGui,
I simply didn't have a need for that)
