cmake_minimum_required(VERSION 2.8)
project(chernobylite)
set(CMAKE_BUILD_TYPE "Release" CACHE STRING "The build type.")
add_definitions("-Werror -fno-strict-aliasing -Wall -Wl,--no-undefined")
include_directories(${chernobylite_SOURCE_DIR}/include)
find_package(OpenCV REQUIRED)
#put impl of all the helpers into library.
add_library(chernobylite SHARED src/chernobylite.cpp)
target_link_libraries(chernobylite ${OpenCV_LIBS})
# add libraries and such.
