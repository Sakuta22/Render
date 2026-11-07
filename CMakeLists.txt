cmake_minimum_required(VERSION 3.20)

project(RenderProject LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(MSVC)
    add_compile_options($<$<CONFIG:Debug>:/fsanitize=address>)
    add_link_options($<$<CONFIG:Debug>:/fsanitize=address>)
endif()

add_executable(RenderApp Sandbox/main.cpp)