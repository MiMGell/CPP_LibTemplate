cmake_minimum_required(VERSION 3.7)

if(${CMAKE_VERSION} VERSION_LESS 3.29)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
else()
    cmake_policy(VERSION 3.29)
endif()

project(Foo
    VERSION 0.1
    DESCRIPTION "a very nice Template"
    LANGUAGES CXX
)

include_directories("include/")

add_library(${PROJECT_NAME}
    "src/foo.cpp"
)