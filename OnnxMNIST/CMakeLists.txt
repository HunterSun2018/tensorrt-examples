cmake_minimum_required(VERSION 3.10)

project(cuda_merkle_tree LANGUAGES CXX CUDA)

find_package( CUDAToolkit REQUIRED)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CUDA_ARCHITECTURES 61)    # for GTX 10xx series

include_directories(${CUDAToolkit_INCLUDE_DIRS})
link_directories(${CUDAToolkit_LIBRARY_DIR})

add_executable(test src/main.cpp common/logger.cpp)

target_link_libraries(test nvinfer nvonnxparser cudart)
