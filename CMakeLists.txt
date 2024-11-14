cmake_minimum_required(VERSION 3.14)

project(qtwebglplugin LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

add_subdirectory(src/plugins/platforms/webgl)
add_subdirectory(tests/plugins/platforms/webgl)
