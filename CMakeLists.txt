cmake_minimum_required(VERSION 3.0.0)

project(Test)

set(Boost_USE_STATIC_LIBS OFF) 
set(Boost_USE_MULTITHREADED ON)  
set(Boost_USE_STATIC_RUNTIME OFF) 
find_package(Boost 1.45.0 COMPONENTS system) 

if(Boost_FOUND)
    include_directories(${Boost_INCLUDE_DIRS}) 
    add_executable(socket src/socket.cpp)
    target_link_libraries(socket ${Boost_LIBRARIES})
endif()

add_executable(Test src/main.cpp)