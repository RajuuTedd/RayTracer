cmake_minimum_required(VERSION 3.18)
project(RayTracerCUDA LANGUAGES CXX CUDA)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CUDA_STANDARD 14)

add_executable(RayTracerCUDA main.cu)

# RTX 2050 -> Ampere target
set_target_properties(RayTracerCUDA PROPERTIES
    CUDA_ARCHITECTURES 86
)

target_compile_options(RayTracerCUDA PRIVATE
    $<$<COMPILE_LANGUAGE:CUDA>:-O2>
)