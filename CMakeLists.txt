cmake_minimum_required(VERSION 3.28)
project(ComputerGraphics)

set(CMAKE_CXX_STANDARD 20)
set(GLAD_DIR vendor/GLAD)

add_executable(ComputerGraphics main.cpp)

# Link GLFW
find_package(glfw3 3.4 REQUIRED)

target_link_libraries(ComputerGraphics glfw)

# Link OpenGL (needed on Windows and Linux)
if (WIN32)
    target_link_libraries(${PROJECT_NAME} opengl32)
elseif(APPLE)
    find_library(OpenGL_LIBRARY OpenGL)
    target_link_libraries(${PROJECT_NAME} ${OpenGL_LIBRARY})
else()
    find_package(OpenGL REQUIRED)
    target_link_libraries(${PROJECT_NAME} OpenGL::GL)
endif()

# Link GLAD
add_library(glad STATIC ${GLAD_DIR}/src/glad.c)
target_include_directories(glad PUBLIC ${GLAD_DIR}/include)

target_link_libraries(ComputerGraphics glad)

