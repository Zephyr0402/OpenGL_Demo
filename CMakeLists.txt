cmake_minimum_required(VERSION 3.16)
project(OpenGL_Demo)

set(CMAKE_CXX_STANDARD 14)

# add_executable(OpenGL_Demo main.cpp)

# Add header files
set(GLEW_H /usr/local/Cellar/glew/2.1.0_1/include/GL)
set(GLFW_H /usr/local/Cellar/glfw/3.3.2/include/GLFW)
include_directories(${GLEW_H} ${GLFW_H})

# Add target linkage
set(GLEW_LINK /usr/local/Cellar/glew/2.1.0_1/lib/libGLEW.2.1.dylib)
set(GLFW_LINK /usr/local/Cellar/glfw/3.3.2/lib/libglfw.3.dylib)
link_libraries(${OPENGL} ${GLEW_LINK} ${GLFW_LINK})

# Exec compile command
set(SOURCE_FILES main.cpp)
add_executable(test ${SOURCE_FILES})

if (APPLE)
    target_link_libraries(test "-framework OpenGL")
    target_link_libraries(test "-framework GLUT")
endif()