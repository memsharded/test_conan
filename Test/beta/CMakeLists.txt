set(PROJECT_NAME beta)
cmake_minimum_required(VERSION 3.26)
project(${PROJECT_NAME} LANGUAGES CXX)

find_package(alpha)

add_library(${PROJECT_NAME} SHARED)

target_sources(${PROJECT_NAME}
	PRIVATE
		beta.cpp
)

target_include_directories(${PROJECT_NAME}
	PUBLIC
		${CMAKE_CURRENT_SOURCE_DIR}/include
)

target_link_libraries(${PROJECT_NAME}
	PUBLIC
		alpha::alpha1_1
)