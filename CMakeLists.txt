cmake_minimum_required(VERSION 3.17)
project(SObjectizerTest)

set(CMAKE_CXX_STANDARD 17)

if (MSVC)
    add_definitions(-D_CRT_SECURE_NO_WARNINGS)
endif ()

set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(${PROJECT_NAME} main.cpp)

find_package(sobjectizer CONFIG REQUIRED)
target_link_libraries(${PROJECT_NAME} PRIVATE sobjectizer::SharedLib)

target_include_directories(${PROJECT_NAME} PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}>)