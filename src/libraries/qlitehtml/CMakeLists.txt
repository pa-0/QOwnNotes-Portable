cmake_minimum_required(VERSION 3.7)
project(qlitehtml VERSION 1.0 LANGUAGES CXX)

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

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(QLITEHTML_EXPORT qlitehtml)
set(QLITEHTML_DEVEL_COMPONENT Devel)
set(QLITEHTML_DEVEL_EXCLUDE_FROM_ALL NO)

if(UNIX OR MINGW)
    include(GNUInstallDirs)
    set(QLITEHTML_BIN_PATH ${CMAKE_INSTALL_BINDIR})
    set(QLITEHTML_LIBRARY_PATH  ${CMAKE_INSTALL_LIBDIR})
    set(QLITEHTML_HEADER_PATH ${CMAKE_INSTALL_INCLUDEDIR}/qlitehtml)
else()
    set(QLITEHTML_BIN_PATH bin)
    set(QLITEHTML_LIBRARY_PATH lib)
    set(QLITEHTML_HEADER_PATH include/qlitehtml)
endif()

find_package(QT 5.11 NAMES Qt6 Qt5 COMPONENTS Widgets REQUIRED)
find_package(Qt${QT_VERSION_MAJOR} COMPONENTS Widgets REQUIRED)
set(Qt Qt${QT_VERSION_MAJOR})

set(QLITEHTML_BUILD_TESTS OFF)
if (QLITEHTML_BUILD_TESTS)
    add_subdirectory(tests/manual/browser)
endif()

add_subdirectory(src)
