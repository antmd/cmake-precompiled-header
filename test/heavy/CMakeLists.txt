cmake_minimum_required(VERSION 2.8)
enable_testing()
project(test-heavy)
include(../../PrecompiledHeader.cmake)
if(MSVC)
  set(pch_source test-pch.cpp)
endif()
add_executable(test-heavy test-heavy.cpp test-pch.h ${pch_source})
add_precompiled_header(test-heavy test-pch.h FORCEINCLUDE)
add_test(test-heavy test-heavy)
