cmake_minimum_required(VERSION 3.21)

project(imgui
    LANGUAGES CXX
    VERSION 1.89
)

option(WITH_STDLIB
    "Compile imgui with 'mist/cpp' helper and include its header"
    ON
)

set(CMAKE_CXX_EXTENSIONS OFF)

add_library(imgui STATIC
    imconfig.h
    imgui_demo.cpp
    imgui_draw.cpp
    imgui_internal.h
    imgui_tables.cpp
    imgui_widgets.cpp
    imgui.cpp
    imgui.h
    imstb_rectpack.h
    imstb_textedit.h
    imstb_truetype.h
)

target_include_directories(imgui PUBLIC
    "$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>"
    "$<INSTALL_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>"
)

set(IMGUI_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR})
if (WITH_STDLIB)
    add_subdirectory("misc/cpp")
    target_link_libraries(imgui PRIVATE IMGUI_STDLIB)
endif()
