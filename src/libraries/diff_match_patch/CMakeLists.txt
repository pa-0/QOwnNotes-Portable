cmake_minimum_required(VERSION 3.5)
project(DiffMatchPatchLib)

set(CompilerFlags
        CMAKE_CXX_FLAGS
        CMAKE_CXX_FLAGS_DEBUG
        CMAKE_CXX_FLAGS_RELEASE
        CMAKE_C_FLAGS
        CMAKE_C_FLAGS_DEBUG
        CMAKE_C_FLAGS_RELEASE
        )
foreach(CompilerFlag ${CompilerFlags})
  string(REPLACE "/MD" "/MT" ${CompilerFlag} "${${CompilerFlag}}")
endforeach()

add_library(diff_match_patch STATIC
    diff_match_patch.h
    diff_match_patch.cpp
)

add_library(Google::DiffMatchPatch ALIAS diff_match_patch)

find_package(Qt${QT_VERSION_MAJOR} REQUIRED COMPONENTS Core)

target_include_directories(diff_match_patch PUBLIC
    ${CMAKE_CURRENT_LIST_DIR}
)

target_link_libraries(diff_match_patch PUBLIC
    Qt${QT_VERSION_MAJOR}::Core
)
