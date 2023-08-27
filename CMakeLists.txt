cmake_minimum_required(VERSION 3.15)
project(sph VERSION 0.1.0 LANGUAGES C CXX)

# MODIFY WITH YOUR OWN VCPKG PATH
include(C:/src/vcpkg/scripts/buildsystems/vcpkg.cmake)

include(CTest)
enable_testing()

add_executable(sph main.cpp)

########################################################

# LIBRARIES
find_package(Eigen3 CONFIG REQUIRED)
target_link_libraries(sph PRIVATE Eigen3::Eigen)

find_package(GLUT REQUIRED)
target_link_libraries(sph PRIVATE GLUT::GLUT)

########################################################

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
