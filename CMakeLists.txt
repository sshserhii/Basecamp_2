cmake_minimum_required(VERSION 2.0)
set(CMAKE_CXX_STANDARD 11)

project(move_test_1)

set(CMAKE_BUILD_TYPE Release)
include_directories(include)
add_compile_options(-std=c++11)

file(GLOB SOURCES "src/*.cpp")
add_library(test_m SHARED ${SOURCES})
install(TARGETS test_m DESTINATION /usr/lib)

set(PROJECT_LINK_LIBS libtest_m.so)
link_directories(~/home/cppbcuser/basecamp/basecamp_3/task2)
include_directories(~/home/cppbcuser/basecamp/basecamp_3/task2/include)

if(EXISTS "/usr/lib/${PROJECT_LINK_LIBS}")
add_executable(main src/main.cpp)
target_link_libraries(main ${PROJECT_LINK_LIBS})
endif() 	
