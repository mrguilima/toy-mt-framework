project(TOY_MT_FRAMEWORK)
cmake_minimum_required(VERSION 2.8)
cmake_policy(SET CMP0042 NEW)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_CURRENT_SOURCE_DIR}/cmake/Modules")
find_package(TBB)
#find_package(CppUnit)

set(Boost_NO_BOOST_CMAKE ON)
find_package(Boost)
include_directories(${Boost_INCLUDE_DIR})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11 -DUSE_VECGEOM_NAVIGATOR ")

add_subdirectory(BusyWaitCalibration)
add_subdirectory(SingleThreadedProcessingDemo)
if(TBB_FOUND)
    add_subdirectory(TBBProcessingDemo)
endif()
