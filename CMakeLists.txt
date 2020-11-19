cmake_minimum_required(VERSION 3.14...3.19)

project(
  CPPTemplate
  VERSION 1.0
  LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

option(PACKAGE_TESTS "Build the tests" ON)

add_subdirectory(src)
add_subdirectory(apps)

if(PACKAGE_TESTS)
    enable_testing()
    include(GoogleTest)
    add_subdirectory(tests)
endif()