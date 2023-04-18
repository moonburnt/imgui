add_library(imgui_stdlib STATIC
    imgui_stdlib.cpp
    imgui_stdlib.h
)

target_include_directories(imgui_stdlib PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${IMGUI_INCLUDE_DIR}
)
