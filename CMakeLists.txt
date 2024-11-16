cmake_minimum_required(VERSION 3.20)

project(setting-up-box2d-sdl3-c LANGUAGES C)
add_executable(app)

# Check for WebAssembly
if (CMAKE_SYSTEM_NAME MATCHES "Emscripten")
    target_include_directories(app PRIVATE E:/libs/box2d-3.0.0-prefix/web/include)
    target_link_directories(app PRIVATE E:/libs/box2d-3.0.0-prefix/web/lib)
endif()

# Check for Windows
if (WIN32)
    target_include_directories(app PRIVATE E:/libs/box2d-3.0.0-prefix/win/include)
    target_link_directories(app PRIVATE E:/libs/box2d-3.0.0-prefix/win/lib)
    target_link_options(app PRIVATE -static)
endif()

target_sources(app
PRIVATE
    src/main.c
)

find_package(SDL3)
target_link_libraries(app PRIVATE box2d SDL3::SDL3)
