cmake_minimum_required(VERSION 3.19)
project(boost_playground)

set(CMAKE_CXX_STANDARD 20)

set(Boost_USE_STATIC_LIBS OFF)
set(Boost_USE_MULTITHREADED ON)
set(Boost_USE_STATIC_RUNTIME OFF)
find_package(Boost 1.71.0 COMPONENTS)

if(Boost_FOUND)
    message("Boost is found ${Boost_VERSION_STRING}")
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(boost_playground main.cpp)
    target_link_libraries(boost_playground ${Boost_LIBRARIES})
endif()