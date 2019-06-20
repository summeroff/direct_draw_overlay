cmake_minimum_required(VERSION 3.10)
project(direct_draw_overlay)

ADD_DEFINITIONS(-DUNICODE)
ADD_DEFINITIONS(-D_UNICODE)

SET(CMAKE_CXX_STANDARD 17)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)
SET(CMAKE_CXX_EXTENSIONS OFF)

file(GLOB SOURCES "*.cpp")

add_executable(direct_draw_overlay WIN32  ${SOURCES} )

target_link_libraries(direct_draw_overlay d2d1.lib dwrite.lib Dwmapi.lib)

set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT direct_draw_overlay)