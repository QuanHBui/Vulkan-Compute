cmake_minimum_required(VERSION 3.10)

project(VulkanCompute)

set(CMAKE_CXX_STANDARD_REQUIRED 17)
set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan)
include_directories(${Vulkan_INCLUDE_DIR})

# For the header and resource files to show up in IDEs
file(GLOB_RECURSE SOURCES "${PROJECT_SOURCE_DIR}/src/*.cpp")
file(GLOB_RECURSE HEADERS "${PROJECT_SOURCE_DIR}/include/*.h")

add_executable(${CMAKE_PROJECT_NAME} ${SOURCES} ${HEADERS} ${GLSL})
target_include_directories(${CMAKE_PROJECT_NAME} PUBLIC "${PROJECT_SOURCE_DIR}/include")

target_link_libraries(${CMAKE_PROJECT_NAME} ${Vulkan_LIBRARY})