cmake_minimum_required(VERSION 3.25)
project(sdl_gl VERSION 0.1.0 LANGUAGES CXX)

add_executable(sdl_gl_demo src/main.cpp)
target_include_directories(
    sdl_gl_demo
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/src
)
set_target_properties(
    sdl_gl_demo
    PROPERTIES
        CXX_STANDARD 20
)

find_package(SDL2 CONFIG REQUIRED COMPONENTS SDL2 SDL2main)
find_package(OpenGL REQUIRED)
find_package(glad REQUIRED)

target_link_libraries(sdl_gl_demo PRIVATE SDL2::SDL2 SDL2::SDL2main)
target_link_libraries(sdl_gl_demo PRIVATE OpenGL::GL)
target_link_libraries(sdl_gl_demo PRIVATE glad::glad)
