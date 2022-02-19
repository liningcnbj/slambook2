# 为使用 sophus，需要使用find_package命令找到它
find_package(Sophus REQUIRED)
# include_directories( ${Sophus_INCLUDE_DIRS} )  #包含头文件目录 这句需要添加
include_directories( "../../3rdparty/Sophus" )    #指定目录

option(USE_UBUNTU_20 "Set to ON if you are using Ubuntu 20.04" ON)
find_package(Pangolin REQUIRED)
if(USE_UBUNTU_20)
    message("You are using Ubuntu 20.04, fmt::fmt will be linked")
    find_package(fmt REQUIRED)
    set(FMT_LIBRARIES fmt::fmt)
endif()
include_directories(${Pangolin_INCLUDE_DIRS})
add_executable(trajectoryError trajectoryError.cpp)
target_link_libraries(trajectoryError ${Pangolin_LIBRARIES} ${FMT_LIBRARIES})
