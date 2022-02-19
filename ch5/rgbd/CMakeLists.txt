set(CMAKE_CXX_FLAGS "-std=c++11")
#寻找opencv库
find_package( OpenCV REQUIRED)
#添加头文件
include_directories(${OpenCV_INCLUDE_DIRS})

find_package(Sophus REQUIRED)
# include_directories(${Sophus_INCLUDE_DIRS})
include_directories( "../../3rdparty/Sophus" )

find_package(Pangolin REQUIRED)

add_executable(joinMap joinMap.cpp)
target_link_libraries(joinMap ${OpenCV_LIBS} ${Pangolin_LIBRARIES})