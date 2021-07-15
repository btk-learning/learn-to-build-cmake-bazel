cmake_minimum_required(VERSION 3.10)

project(main)

set(CMAKE_CXX_FLAGS "-Wall -Wmissing-include-dirs -Ipath/that/doesnt/exist")

set(SOURCES main.cpp)
add_executable( main ${SOURCES})