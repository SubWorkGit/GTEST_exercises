cmake_minimum_required(VERSION 3.14)
project(my_project)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


include(FetchContent)

FetchContent_Declare(
    googletest
    URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

add_executable(
    sample2_unittest
    sample2_unittest.cc
    sample2.cc
)

target_include_directories(sample2_unittest PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(
    sample2_unittest
    GTest::gtest_main
)

#enable CMake’s test runner to discover the tests included in the binary, 
#using the GoogleTest CMake module.
include(GoogleTest)
gtest_discover_tests(sample2_unittest)

