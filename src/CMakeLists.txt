cmake_minimum_required(VERSION 3.10)

project(main)

set(CMAKE_CXX_FLAGS "-Wall -Wmissing-include-dirs -Ipath/that/doesnt/exist")

include_directories(${CMAKE_SOURCE_DIR})

add_library(test OBJECT "test.cpp")


set(SOURCES main.cpp)
add_executable( main ${SOURCES})
target_link_libraries(main test)