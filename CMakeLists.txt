# ------------------------------------------------------------------------------
# CMake basic options
# ------------------------------------------------------------------------------
cmake_minimum_required(VERSION 3.5.0)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

# Register custom cmake commands
find_package(Git REQUIRED)
include(GetGitRevisionDescription)

# ------------------------------------------------------------------------------
# Project description and (meta) information
# ------------------------------------------------------------------------------

# Get git revision
get_git_head_revision(GIT_REFSPEC GIT_SHA1)
string(SUBSTRING "${GIT_SHA1}" 0 12 GIT_REV)
if(NOT GIT_SHA1)
    set(GIT_REV "0")
endif()

# Meta information about the project
# cmake-format: off
set(META_PROJECT_NAME        "qtextra")
set(META_PROJECT_DESCRIPTION "Qt Extra components and widgets")
set(META_VERSION_MAJOR       "0")
set(META_VERSION_MINOR       "0")
set(META_VERSION_PATCH       "1")
set(META_VERSION_REVISION    "${GIT_REV}")
set(META_VERSION             "${META_VERSION_MAJOR}.${META_VERSION_MINOR}.${META_VERSION_PATCH}")
set(META_NAME_VERSION        "${META_PROJECT_NAME} v${META_VERSION} (${META_VERSION_REVISION})")
set(META_CMAKE_INIT_SHA      "${GIT_REV}")
# cmake-format: on

string(MAKE_C_IDENTIFIER ${META_PROJECT_NAME} META_PROJECT_ID)
string(TOUPPER ${META_PROJECT_ID} META_PROJECT_ID)

message("=> Project : ${META_NAME_VERSION}")

# ------------------------------------------------------------------------------
# Project configuration options
# ------------------------------------------------------------------------------
# Project options
# cmake-format: off
option(OPTION_BUILD_EXAMPLES "Build examples."                                        OFF)
# cmake-format: on

# The default build type provided by CMake is to include no compiler flags for
# optimization. For some projects you may want to set a default build type so
# that you do not have to remember to set it.
if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
    message(
            STATUS "Setting build type to 'RelWithDebInfo' as none was specified.")
    set(CMAKE_BUILD_TYPE
            RelWithDebInfo
            CACHE STRING "Choose the type of build." FORCE)
    # Set the possible values of build type for cmake-gui
    set_property(CACHE CMAKE_BUILD_TYPE PROPERTY STRINGS "Debug" "Release"
            "MinSizeRel" "RelWithDebInfo")
endif()

# ------------------------------------------------------------------------------
# Project Declaration
# ------------------------------------------------------------------------------

project(${META_PROJECT_NAME}
        VERSION ${META_VERSION}
        LANGUAGES CXX)

# Set output directories
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR})

# Create version file
file(WRITE "${PROJECT_BINARY_DIR}/VERSION" "${META_NAME_VERSION}")


# ------------------------------------------------------------------------------
# Build instructions
# ------------------------------------------------------------------------------

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

if(CMAKE_VERSION VERSION_LESS "3.7.0")
    set(CMAKE_INCLUDE_CURRENT_DIR ON)
endif()

# ------------------------------------------------------------------------------
# External dependencies
# ------------------------------------------------------------------------------

find_package(Qt5 COMPONENTS Widgets Network REQUIRED)

# ------------------------------------------------------------------------------
# Project modules
# ------------------------------------------------------------------------------

add_subdirectory(qtcoreextra)
add_subdirectory(qtplugins)
add_subdirectory(qtwidgetsextra)
add_subdirectory(qtpropertybrowser)
# unused so skip it
#add_subdirectory(qtsqlextra)
#add_subdirectory(qtsqlwidgets)
#add_subdirectory(modelexporters)

if (OPTION_BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()
