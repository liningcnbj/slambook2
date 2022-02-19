set(CMAKE_CXX_FLAGS "-std=c++11")
#寻找opencv库
find_package( OpenCV REQUIRED)
#添加头文件
include_directories(${OpenCV_INCLUDE_DIRS})

find_package(Pangolin REQUIRED)

add_executable(stereoVision stereoVision.cpp)
target_link_libraries(stereoVision ${OpenCV_LIBS} ${Pangolin_LIBRARIES})