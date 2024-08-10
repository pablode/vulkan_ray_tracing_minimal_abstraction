# Vulkan Ray Tracing Minimal Abstraction

<p float="left">
  <img src="resources/render_1.png" width="250">
  <img src="resources/render_2.png" width="250">
</p>

**ray_pipeline** uses the ray tracing pipeline to generate the final image.

**ray_query** uses the graphics pipeline along with ray querying to generate the final image.

**headless** generates a ray traced image without creating a window or needing a surface.

## Important Note

Make sure the **VK_KHR_ray_query** and  **VK_KHR_ray_tracing_pipeline** extensions are available on your device!

**Even if you have a compatible RTX / RX graphics card, your drivers may not have the extension available.**

To see if the extension is available, you can use the **vulkaninfo** binary.

![vulkaninfo](resources/vulkaninfo.png)

## Dependencies

* Graphics Drivers with Vulkan Support (AMD, NVIDIA, MESA, etc...)
* [Vulkan SDK](https://vulkan.lunarg.com/home/welcome)
  * [Vulkan Headers](https://github.com/KhronosGroup/Vulkan-Headers)
  * [Vulkan Loader](https://github.com/KhronosGroup/Vulkan-Loader)
  * [glslang](https://github.com/KhronosGroup/glslang)
  * [Vulkan Validation Layers (if you want to enable validation layers)](https://github.com/KhronosGroup/Vulkan-ValidationLayers)

### Windows

* [Visual Studio 2022](https://visualstudio.microsoft.com/vs/)

### Linux

* X11

## Building

Navigate to a subproject:
```bash
cd vulkan_ray_tracing_minimal_abstraction/ray_pipeline
# or cd vulkan_ray_tracing_minimal_abstraction/ray_query
# or cd vulkan_ray_tracing_minimal_abstraction/headless
```

Create a build directory and navigate to the new directory.
```bash
mkdir build
cd build
```
Run cmake with the root of the repository as the argument. You can now use the make file generated by CMake.
```bash
cmake .. -D VALIDATION_ENABLED=1

# on Linux
make

# on Windows
cmake --build .
```

#### Image generated from headless example:
![headless](resources/headless.png)
