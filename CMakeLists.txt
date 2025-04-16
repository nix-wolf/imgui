cmake_minimum_required(VERSION 3.30)
project(imgui LANGUAGES CXX)

set(IMGUI_SOURCES
       backends/imgui_impl_opengl3.h
       backends/imgui_impl_opengl3.cpp
       backends/imgui_impl_opengl3_loader.h
       backends/imgui_impl_glfw.h
       backends/imgui_impl_glfw.cpp
       imgui.h
       imconfig.h
       imgui.cpp
       imgui_internal.h
       imgui_draw.cpp
       imgui_tables.cpp
       imgui_widgets.cpp
       imgui_demo.cpp
       imstb_rectpack.h
       imstb_textedit.h
       imstb_truetype.h
)

add_library(imgui STATIC ${IMGUI_SOURCES})
target_compile_definitions(imgui PRIVATE IMGUI_IMPL_OPENGL_LOADER_GLAD)
target_include_directories(imgui PUBLIC . backends)
target_link_libraries(imgui PUBLIC glfw)
