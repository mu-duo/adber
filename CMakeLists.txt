cmake_minimum_required(VERSION 3.29)
set(CMAKE_CXX_STANDARD 17)

project(ADBER VERSION 0.0.1)

# 添加宏定义
# add_definitions(-DSFML_STATIC )

# =====================================================================
# target_include_directories(SFML-2.6.1)
# =====================================================================
# add head
include_directories(${CMAKE_SOURCE_DIR}/SFML-2.6.1/include)

# add lib
link_directories("${CMAKE_SOURCE_DIR}/SFML-2.6.1/lib")
message(${CMAKE_SOURCE_DIR}/SFML-2.6.1/lib)

# add lib
set (
    LIBRARIES
    sfml-main
    sfml-audio
    sfml-graphics
    sfml-network
    sfml-system
    sfml-window
)

file(GLOB ALL_LIBRARIES "${CMAKE_SOURCE_DIR}/SFML-2.6.1/lib/*.a")
foreach(LIB ${ALL_LIBRARIES})
    if(NOT LIB MATCHES "libsfml.*.a$")
        list(APPEND LIBRARIES "${LIB}")
    endif()
endforeach()

foreach(LIB ${LIBRARIES})
    message("use library: ${LIB}")
endforeach()

link_libraries(${FILTERED_LIBRARIES})
set(SRC_LIST         main.cpp)
add_executable(${PROJECT_NAME} ${SRC_LIST})
