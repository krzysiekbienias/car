# unit_tests/CMakeLists.txt
if(NOT EXISTS "${CMAKE_CURRENT_SOURCE_DIR}/test_smoke.cpp")
    message(STATUS "No tests yet (create unit_tests/test_smoke.cpp to enable tests).")
    return()
endif()

find_package(GTest REQUIRED)

add_executable(unit_tests test_smoke.cpp)

target_link_libraries(unit_tests
        PRIVATE car_lib GTest::gtest GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(unit_tests)