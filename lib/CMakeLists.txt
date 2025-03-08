add_library(adder src/adder.cpp include/adder.h)
target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR}/lib/include)
