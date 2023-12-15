# Version
cmake_minimum_required(VERSION 3.5)

# Project
project(project_name VERSION 0.0.1
                    DESCRIPTION "Cmake Example"
                    LANGUAGES CXX)
if(NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release CACHE STRING "" FORCE)
endif()
message(STATUS "CMAKE_BUILD_TYPE: ${CMAKE_BUILD_TYPE}")

# Libraries
add_library(cxx_setup INTERFACE)
target_compile_options(cxx_setup
  INTERFACE -Wall )
target_compile_features(cxx_setup INTERFACE cxx_std_17)
target_include_directories(cxx_setup
  INTERFACE ${PROJECT_SOURCE_DIR})

# Tests

# Installation

# 💡 Some things (e.g. tests or installation) are missing here.
# 🚨 Make sure CMakeLists.txt file exists in the subdirectories!
add_subdirectory(${PROJECT_NAME})
add_subdirectory(executables)
