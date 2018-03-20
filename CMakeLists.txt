cmake_minimum_required(VERSION 3.5.1)

project (CmakeProject)
set (CMAKE_CXX_STANDART 17)

set (SOURCE_FILES
	A/script.py;
	B/main.cpp
)

execute_process(
	COMMAND python script.py WORKING_DIRECTORY A
)

include_directories(A)
include_directories(B)

add_executable(CmakeProject ${SOURCE_FILES})

target_include_directories(CmakeProject PUBLIC ${PROJECT_SOURCE_DIR})
