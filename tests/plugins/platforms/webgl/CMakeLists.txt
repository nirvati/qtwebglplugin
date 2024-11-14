cmake_minimum_required(VERSION 3.14)

project(webgl_tests LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Gui Quick Test WebSockets)

add_executable(tst_webgl
    tst_webgl.cpp
    parameters.h
    basic_scene.qml
    colors.qml
    launcher.qml
    LauncherList.qml
    SimpleLauncherDelegate.qml
    images/back.png
    images/next.png
)

target_include_directories(tst_webgl PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(tst_webgl PRIVATE
    Qt6::Core
    Qt6::Gui
    Qt6::Quick
    Qt6::Test
    Qt6::WebSockets
)

set_target_properties(tst_webgl PROPERTIES
    OUTPUT_NAME "tst_webgl"
)
