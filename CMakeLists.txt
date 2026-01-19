cmake_minimum_required(VERSION 3.20)
project(car LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(APPLE AND EXISTS "/opt/homebrew")
    list(PREPEND CMAKE_PREFIX_PATH "/opt/homebrew")
endif()

option(ENABLE_APP "Build app/playground" ON)

if(ENABLE_APP AND EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/app/main.cpp")
    add_executable(car_app app/main.cpp)
    target_link_libraries(car_app PRIVATE car_lib)
endif()

option(ENABLE_TESTS "Build unit tests" ON)

add_library(car_lib INTERFACE)
target_include_directories(car_lib INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}/header)

if(ENABLE_TESTS AND EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/unit_tests/CMakeLists.txt")
    enable_testing()
    add_subdirectory(unit_tests)
endif()