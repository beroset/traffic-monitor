cmake_minimum_required(VERSION 3.1)
project(test_background_subtractor)

set(SOURCE_FILES
        BackgroundSubtractorTest.cpp
        main.cpp)

set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
add_executable(test_background_subtractor ${SOURCE_FILES})

target_link_libraries(test_background_subtractor lib-traffic-monitor
        core-traffic-monitor
        ${GTEST_LIBRARIES}
        ${OpenCV_LIBS}
	${CMAKE_THREAD_LIBS_INIT})
enable_testing()
add_test(NAME test_background_subtractor COMMAND test_background_subtractor)
