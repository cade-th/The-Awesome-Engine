cmake_minimum_required(VERSION 3.13.4)

project(OLAS)

add_executable(${PROJECT_NAME} src/main.cpp)

add_subdirectory(external/glfw)

add_subdirectory(external/glad)

target_include_directories(${PROJECT_NAME} 
    PUBLIC external/glfw/include
    PUBLIC external/glad/include/glad
    PUBLIC external/glad/include/KHR)

target_link_directories(${PROJECT_NAME} 
    PRIVATE external/glfw/src
    PRIVATE external/glad/src)

target_link_libraries(${PROJECT_NAME} 
    glfw
    glad
    )