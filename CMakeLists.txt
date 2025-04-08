cmake_minimum_required(VERSION 3.15)
project(opengl_playground)

set(CMAKE_CXX_STANDARD 20)

# Include GLFW headers
include_directories(${CMAKE_SOURCE_DIR}/include)

# Add main.cpp
add_executable(${PROJECT_NAME} src/main.cpp)

# Link static GLFW lib and macOS frameworks
target_link_libraries(${PROJECT_NAME}
        ${CMAKE_SOURCE_DIR}/libs/libglfw3.a
        "-framework Cocoa"
        "-framework OpenGL"
        "-framework IOKit"
        "-framework CoreVideo"
)
