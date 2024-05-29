cmake_minimum_required(VERSION 3.22.1)
project(openGL_vbuffers)
cmake_policy(SET CMP0072 NEW)

find_package(OpenGL REQUIRED)

add_definitions(-DGLEW_STATIC) # glew preprocessor definition (may not be nessecary)

set(SOURCE_FILES 
    src/Renderer.cpp
    src/IndexBuffer.cpp
    src/VertexBuffer.cpp
)

add_executable(openGL_vbuffers ${SOURCE_FILES} src/main.cpp)

target_link_libraries(openGL_vbuffers
    GLEW
    glfw
    OpenGL::GL
)
