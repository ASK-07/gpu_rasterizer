cmake_minimum_required(VERSION 3.20)

project(GPURasterizer)

set(CMAKE_CXX_STANDARD 20)

set(VULKAN_SDK_PATH $ENV{VULKAN_SDK})

find_package(Vulkan REQUIRED)

add_subdirectory(external/glfw)

add_executable(GPURasterizer
    src/main.cpp
)

target_include_directories(GPURasterizer PRIVATE
    ${VULKAN_SDK_PATH}/Include
)

target_link_libraries(GPURasterizer glfw Vulkan::Vulkan)