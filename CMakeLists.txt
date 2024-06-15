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

target_include_directories(${LIBRARY_NAME}
    PRIVATE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
    PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
    $<INSTALL_INTERFACE:include>
)

install(DIRECTORY include/ DESTINATION include)