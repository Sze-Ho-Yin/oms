cmake_minimum_required(VERSION 3.28)
project(oms)

set(CMAKE_CXX_STANDARD 20)

add_executable(oms src/main.cpp)

#enable test module
find_package(GTest REQUIRED)
include_directories(${GTEST_INCLUDE_DIRS})
# Add the test executable
add_executable(SimpleProjectTests tests/test_main.cpp)
target_link_libraries(SimpleProjectTests ${GTEST_LIBRARIES} pthread)

# Enable testing
enable_testing()
add_test(NAME MyTests COMMAND SimpleProjectTests)