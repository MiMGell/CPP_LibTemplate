cmake_minimum_required(VERSION 3.7)

if(${CMAKE_VERSION} VERSION_LESS 3.29)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
else()
    cmake_policy(VERSION 3.29)
endif()

set(LIBRARY_NAME foo)

set(LIBRARY_VERSION 1.0.0)

set(SOURCES
  src/foo.cpp
)

include_directories(
    PUBLIC
    "include/foo.h"
)

add_library(${LIBRARY_NAME} ${SOURCES})

set_target_properties(${LIBRARY_NAME} PROPERTIES
  VERSION ${LIBRARY_VERSION}
  SOVERSION ${LIBRARY_VERSION}
  OUTPUT_NAME ${LIBRARY_NAME}
)