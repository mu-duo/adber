cmake_minimum_required(VERSION 3.29)
set(CMAKE_CXX_STANDARD 17)

project(ADBER VERSION 0.0.1)
set(SRC_LIST main.cpp)

# target_include_directories(SFML-2.6.1)
# add head
include_directories(${CMAKE_SOURCE_DIR}/SFML-2.6.1/include)

# add lib
link_directories(${CMAKE_SOURCE_DIR}/SFML-2.6.1/lib)

find_library(SFML NAMES ${CMAKE_SOURCE_DIR}/SFML-2.6.1/include/SFML PATHS ${CMAKE_SOURCE_DIR}/SFML-2.6.1/lib)



add_executable(${PROJECT_NAME} ${SRC_LIST})
