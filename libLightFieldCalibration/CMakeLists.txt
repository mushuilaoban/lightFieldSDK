# author: Clemens Brummer
# date:   18.10.2012

cmake_minimum_required(VERSION 2.6)
project(libLightFieldCalibration)

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIR})
link_directories(${OpenCV_LIB_DIR})

add_definitions(-D_CRT_SECURE_NO_WARNINGS)

file(GLOB SRC_FILES src/*.c*)
file(GLOB HDR_FILES src/*.h*)


add_library(${PROJECT_NAME} STATIC ${SRC_FILES} ${HDR_FILES})
target_link_libraries(${PROJECT_NAME} ${OpenCV_LIBS})