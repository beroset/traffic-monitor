cmake_minimum_required(VERSION 3.1)
project(test_transform)

set(SOURCE_FILES main.cpp)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
add_executable(test_transform ${SOURCE_FILES})

target_link_libraries(test_transform lib-traffic-monitor
        core-traffic-monitor
        ${GTEST_LIBRARIES}
        ${OpenCV_LIBS}
	${CMAKE_THREAD_LIBS_INIT})

enable_testing()
add_test(NAME test_transform COMMAND test_transform)
