cmake_minimum_required(VERSION 3.18.0)
project(cmakeExampleLibExecutable VERSION 0.1.0 LANGUAGES CXX)

# for concepts, edit to suit your need
set(CMAKE_CXX_STANDARD 20)

include(CTest)
enable_testing()

include_directories(src/include)

add_library(funcs src/include/funcs.hpp)
add_executable(example example.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

target_link_libraries(example funcs)
