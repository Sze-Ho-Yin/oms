cmake_minimum_required(VERSION 3.28)
project(oms)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_executable(oms src/main.cpp)
#enable test module
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})
# Add the test executable
add_executable(oms test/mainTest.cpp)
target_link_libraries(oms ${GTEST_LIBRARIES} pthread)

## Enable testing
#enable_testing()
#add_test(NAME MyTests COMMAND SimpleProjectTests)