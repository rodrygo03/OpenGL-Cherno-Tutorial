cmake_minimum_required(VERSION 3.22.1)
project(openGL)
cmake_policy(SET CMP0072 NEW)

find_package(OpenGL REQUIRED)

add_definitions(-DGLEW_STATIC) # glew preprocessor definition (may not be nessecary)

set(SOURCE_FILES 
    src/Renderer.cpp
    src/IndexBuffer.cpp
    src/VertexBuffer.cpp
    src/VertexArray.cpp
    src/VertexBufferLayout.h
    src/Shader.cpp
)

add_executable(openGL ${SOURCE_FILES} src/main.cpp)

target_link_libraries(openGL
    GLEW
    glfw
    OpenGL::GL
)
