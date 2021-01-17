cmake_minimum_required(VERSION 3.17)
project(receiver)

set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_VERBOSE_MAKEFILE ON)

find_package(Boost COMPONENTS system)
if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(receiver main.cpp)
    target_link_libraries(receiver ${Boost_LIBRARIES})
endif()
