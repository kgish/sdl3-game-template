# sdl3-game-template

This is a basic SDL3 game starters kit implemented using SDL3 and CMake with vcpkg integration and SDL main callbacks.

Special thanks go to [Codotaku](https://www.youtube.com/@Codotaku) and his amazing video tutorials.

## Setup

## Clion

After creating a new C++ 23 project in CLion, go to Settings -> Tools -> Actions on save, and enable the first four
options.

* Reformat code
* Optimize imports
* Rearrange code
* Run code cleanup

### Initialize Git

```
$ git init
```

### Install vcpkg

Add the submodule GitHub repository.

```
$ git submodule add https://github.com/microsoft/vcpkg.git
```

Run the bootstrap script.

```
./vcpkg/bootstrap-vcpkg.sh
```

Add dependencies and project files.

```
./vcpkg/vcpkg new --application
```

### The `CMakePresets.json` file

```
$ cat CMakePresets.json
{
  "version": 3,
  "configurePresets": [
    {
      "name": "vcpkg",
      "generator": "Ninja",
      "binaryDir": "${sourceDir}/build",
      "cacheVariables": {
        "CMAKE_TOOLCHAIN_FILE": "./vcpkg/scripts/buildsystems/vcpkg.cmake"
      }
    }
  ]
}
```

### The .gitignore file

```
$ cat .gitignore
build
.idea
```

## References

* [Simple DirectMedia Layer](https://www.libsdl.org/)
* [Setup SDL 3 GPU with CMake and vcpkg in C++ with SDL main callbacks](https://www.youtube.com/watch?v=90mzOdzdJsc)
* [Install and use packages with CMake](https://learn.microsoft.com/en-us/vcpkg/get_started/get-started?pivots=shell-powershell)