cmake_minimum_required(VERSION 3.15)
project(cube_connect)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
# set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} /MD")

# Include the directories from the dependencies
include(${CMAKE_BINARY_DIR}/conan_toolchain.cmake)


# Print the variable
message(STATUS "MY_VARIABLE: ${CMAKE_INCLUDE_PATH}")

# Link libraries
find_package(glfw3)
find_package(glad)
find_package(glm)
find_package(assimp)
find_package(stb)
find_package(imgui)

add_subdirectory(src)
target_compile_definitions(${PROJECT_NAME} PRIVATE CONFIGURATION="$(ConfigurationName)")
