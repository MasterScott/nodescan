cmake_minimum_required(VERSION 2.8)
project(nodescan)

enable_testing()

if(NOT NODESCAN_USE_LOG)
	set(NODESCAN_USE_LOG 0)
endif()

include(CMakeCompilers.txt)
include(CMakeRequiredLibraries.txt)

include_directories(${CMAKE_SOURCE_DIR}/src/include)
include_directories(${CMAKE_BINARY_DIR}/src/include)

add_subdirectory(src)
if (NOT (DEFINED NO_TESTS OR NO_TESTS))
	add_subdirectory(tests)
endif()
if (NOT (DEFINED NO_TOOLS OR NO_TOOLS))
	add_subdirectory(tools)
endif()
add_subdirectory(bindings)
