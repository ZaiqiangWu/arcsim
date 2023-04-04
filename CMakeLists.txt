cmake_minimum_required(VERSION 3.10.0)
project(arcsim)
set (CMAKE_CXX_STANDARD 11)



find_package(OpenMP REQUIRED)


if(OpenMP_FOUND)
    set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} ${OpenMP_C_FLAGS}")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
endif()
file(GLOB SOURCE ./src/*.cpp ./src/*.hpp)
target_include_directories(./external/alglib)


target_add_executable(arcsim ${SOURCE})