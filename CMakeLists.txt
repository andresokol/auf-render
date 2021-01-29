cmake_minimum_required(VERSION 3.17)
project(vulkan_demo)

set(CMAKE_CXX_STANDARD 20)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
find_package(glm REQUIRED)
find_package(Vulkan REQUIRED)

file(GLOB SOURCES "*/*.cpp")
file(GLOB HEADERS "*/*.hpp")

message(sources ${SOURCES})
message(headers ${HEADERS})

add_executable(${PROJECT_NAME} main.cpp ${HEADERS} ${SOURCES})
target_link_libraries(${PROJECT_NAME} Threads::Threads)
target_link_libraries(${PROJECT_NAME} glfw)
target_link_libraries(${PROJECT_NAME} glm)
target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)
