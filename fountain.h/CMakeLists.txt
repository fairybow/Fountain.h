# fountain.h -- C Fountain screenplay parser
cmake_minimum_required(VERSION 3.21)
project(fountain.h LANGUAGES C)

set(CMAKE_C_STANDARD 99)
set(CMAKE_C_STANDARD_REQUIRED ON)

# --- Library ---

add_library(fountain_h STATIC
    src/fountain.c
    src/fountain-html.c
)

target_include_directories(fountain_h PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

# --- Test executable ---

add_executable(fountain_test test_fountain.c)
target_link_libraries(fountain_test PRIVATE fountain_h)