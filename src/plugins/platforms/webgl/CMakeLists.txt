cmake_minimum_required(VERSION 3.14)

project(qwebgl LANGUAGES CXX)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

find_package(Qt6 REQUIRED COMPONENTS Core Gui WebSockets)

add_library(qwebgl SHARED
    qwebglcontext.cpp
    qwebglfunctioncall.cpp
    qwebglhttpserver.cpp
    qwebglintegration.cpp
    qwebglmain.cpp
    qwebglplatformservices.cpp
    qwebglscreen.cpp
    qwebglwebsocketserver.cpp
    qwebglwindow.cpp
    qwebgl.qrc
)

target_include_directories(qwebgl PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(qwebgl PRIVATE
    Qt6::Core
    Qt6::Gui
    Qt6::WebSockets
)

set_target_properties(qwebgl PROPERTIES
    OUTPUT_NAME "qwebgl"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/plugins/platforms"
)
