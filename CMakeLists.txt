cmake_minimum_required(VERSION 3.17)
project(vulkan_demo)

#set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -O1")

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)
find_package(glm REQUIRED)
find_package(Vulkan REQUIRED)

#include_directories(${PROJECT_SOURCE_DIR}/src)
#include_directories(${PROJECT_SOURCE_DIR})
#
#file(GLOB SOURCES "*/*.cpp")
#file(GLOB HEADERS "*/*.hpp")
#
#message(sources ${SOURCES})
#message(headers ${HEADERS})

add_executable(${PROJECT_NAME} main.cpp src/application.hpp src/application.cpp ${HEADERS} ${SOURCES})
target_link_libraries(${PROJECT_NAME} Threads::Threads)
target_link_libraries(${PROJECT_NAME} glfw)
target_link_libraries(${PROJECT_NAME} glm)
target_link_libraries(${PROJECT_NAME} Vulkan::Vulkan)
