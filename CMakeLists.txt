cmake_minimum_required(VERSION 3.16)
project(plot)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()
aux_source_directory(${CMAKE_CURRENT_SOURCE_DIR} srcs)

add_executable(plot ${srcs})
SET(QT5_MODULES Widgets PrintSupport)
FIND_PACKAGE(Qt5 REQUIRED COMPONENTS ${QT5_MODULES})

TARGET_LINK_LIBRARIES(
        plot
        Qt5::Widgets
        Qt5::PrintSupport
)