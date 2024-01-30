cmake_minimum_required( VERSION 3.27.2)
project(pngdib VERSION 3.1.0)

find_package(ZLIB REQUIRED)
find_package(PNG REQUIRED)

add_library(${PROJECT_NAME} STATIC
	pngdib.c pngdib.h
)

target_include_directories(${PROJECT_NAME} INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

target_link_libraries(${PROJECT_NAME} PRIVATE ZLIB::ZLIB)
target_link_libraries(${PROJECT_NAME} PRIVATE PNG::PNG)



