cmake_minimum_required(VERSION 3.13)
project(receiver)

set(CMAKE_CXX_STANDARD 14)
#set(CMAKE_VERBOSE_MAKEFILE ON)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

find_package(Boost COMPONENTS system)

if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(receiver main.cpp)
    target_link_libraries(receiver ${Boost_LIBRARIES} Threads::Threads)
endif()
