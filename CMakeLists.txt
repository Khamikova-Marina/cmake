cmake_minimum_required(VERSION 3.14)
project(Project_2 VERSION 1.0.0 LANGUAGES CXX)
option(WITH_EXAMPLES "Compile examples" ON)
# set(SOURCE_EXE "myprogram.cpp")
set(SOURCE_LIB "first.cpp" "second.cpp" "hello.hpp")

add_library(hello STATIC "${SOURCE_LIB}")
target_include_directories(hello PUBLIC ${CMAKE_SOURCE_DIR})
#[[
add_executable(myprogram "${SOURCE_EXE}" "hello.hpp")
add_executable(newprogram "newprogram.cpp" "hello.hpp")

target_link_libraries(myprogram hello)
target_link_libraries(newprogram hello)]]

if(WITH_EXAMPLES)
    add_subdirectory(examples)
endif()
