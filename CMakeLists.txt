cmake_minimum_required(VERSION 3.16)

project(coretrace_ci_consumer C)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)
set(CMAKE_C_EXTENSIONS OFF)

add_library(consumer_utils STATIC src/utils.c)
target_include_directories(consumer_utils PUBLIC include)

add_executable(consumer_app src/main.c)
target_link_libraries(consumer_app PRIVATE consumer_utils)

