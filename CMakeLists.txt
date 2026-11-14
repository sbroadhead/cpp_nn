cmake_minimum_required(VERSION 4.3)
project(nn)

set(CMAKE_CXX_STANDARD 26)

include(FetchContent)

FetchContent_Declare(
        eigen
        GIT_REPOSITORY https://gitlab.com/libeigen/eigen.git
        GIT_TAG 3.4.0
        GIT_SHALLOW TRUE
)

set(EIGEN_BUILD_DOC OFF CACHE BOOL "" FORCE)
set(BUILD_TESTING OFF CACHE BOOL "" FORCE)
set(EIGEN_BUILD_PKGCONFIG OFF CACHE BOOL "" FORCE)

FetchContent_MakeAvailable(eigen)

add_executable(nn src/main.cpp)
target_link_libraries(nn PRIVATE Eigen3::Eigen)
