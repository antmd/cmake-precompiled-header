cmake_minimum_required(VERSION 2.8)
enable_testing()
project(test-c-force)
include(../../PrecompiledHeader.cmake)
if(MSVC)
  set(pch_source test-pch.c)
endif()
add_executable(test-c-force test-c-force.c test-pch.h ${pch_source})
add_precompiled_header(test-c-force test-pch.h FORCEINCLUDE)
add_test(test-c-force test-c-force)
