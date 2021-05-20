cmake_minimum_required(VERSION 3.0.0)
#project(ex1 VERSION 0.1.0)
#add_library(ex1 SHARED src/main.cpp)
#set_target_properties(ex1 PROPERTIES RUNTIME_OUTPUT_DIRECTORY ../obj)
#project(ex2 VERSION 0.1.0)
#add_executable(ex2 src/main.cpp obj/.)
#set_target_properties(ex2 PROPERTIES RUNTIME_OUTPUT_DIRECTORY ../bin)

project(Myproject)

add_library(mylib SHARED src/main.cpp)

set_target_properties(mylib PROPERTIES RUNTIME_OUTPUT_DIRECTORY ../obj)

add_executable(myexe src/main.cpp)

set_target_properties(myexe PROPERTIES RUNTIME_OUTPUT_DIRECTORY ../bin)

target_link_libraries(myexe mylib)


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
message("CMAKE_SOURCE_DIR= ${CMAKE_SOURCE_DIR}")
message("CMAKE_BINARY_DIR= ${CMAKE_BINARY_DIR}")
include(CPack)
