CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(Raycaster)

SET(CMAKE_BUILD_TYPE, Development)
SET(CMAKE_CXX_STANDARD 11)

SET(PROJECT_SOURCE_DIR ${PROJECT_OUTPUT_PATH}/Raycaster)
FILE(GLOB_RECURSE SOURCES ${PROJECT_NAME}/*.cpp)
INCLUDE_DIRECTORIES(${PROJECT_NAME})

ADD_EXECUTABLE(raycaster ${SOURCES})

FIND_PACKAGE(SDL2)

if (SDL2_FOUND)
    INCLUDE_DIRECTORIES(${SDL2_INCLUDE_DIRS})
    TARGET_LINK_LIBRARIES(raycaster ${SDL2_LIBRARIES})
endif (SDL2_FOUND)



