cmake_minimum_required(VERSION 3.13)
project(sender)

set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_VERBOSE_MAKEFILE ON)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

find_package(Boost COMPONENTS system)

if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(sender main.cpp)
    target_link_libraries(sender ${Boost_LIBRARIES} Threads::Threads)
endif()
