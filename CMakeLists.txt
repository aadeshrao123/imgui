cmake_minimum_required(VERSION 3.0)
project(imgui)

file(GLOB imgui_src
    "imgui*.cpp"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_opengl3.cpp"
)

add_library(imgui STATIC ${imgui_src})
target_include_directories(imgui PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}
    ${CMAKE_CURRENT_SOURCE_DIR}/backends
)
target_link_libraries(imgui PUBLIC glfw ${OPENGL_gl_LIBRARY})
