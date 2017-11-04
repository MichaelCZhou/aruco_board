CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

set( CMAKE_BUILD_TYPE "Debug" )
PROJECT(demo)
set( CMAKE_CXX_FLAGS "-std=c++11")
# Eigen
include_directories( "/usr/include/eigen3" )


#set(CMAKE_PREFIX_PATH "/usr/local/opencv3/share/OpenCV")
#set(CMAKE_PREFIX_PATH "/home/xjh/library/opencv-3.1_OpenMP/build")

FIND_PACKAGE(OpenCV 3 REQUIRED)# HINTS "/usr/local/opencv3.1/shared/OpenCV")

message("include_dir = " ${OpenCV_INCLUDE_DIRS})

add_executable( detect_board detect_board.cpp )
target_link_libraries( detect_board ${OpenCV_LIBS} )

add_executable( calibrate_camera calibrate_camera.cpp )
target_link_libraries( calibrate_camera ${OpenCV_LIBS} )

add_executable( create_board create_board.cpp )
target_link_libraries( create_board ${OpenCV_LIBS} )

add_executable( calibrate_camera_charuco calibrate_camera_charuco.cpp )
target_link_libraries( calibrate_camera_charuco ${OpenCV_LIBS} )

add_executable( detect_board_charuco detect_board_charuco.cpp )
target_link_libraries( detect_board_charuco ${OpenCV_LIBS} )

add_executable( detect_markers detect_markers.cpp )
target_link_libraries( detect_markers ${OpenCV_LIBS} )

#INCLUDE_DIRECTORIES( ${PROJECT_SOURCE_DIR}/include)
#add_executable( test_chessboardgenerator test_chessboardgenerator.cpp )
#target_link_libraries( test_chessboardgenerator ${OpenCV_LIBS} )


