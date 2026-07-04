set(LIBRARY_NAME imgui)

file(GLOB BBRX_CMAKE_CURRENT_SOURCES
		"${CMAKE_CURRENT_SOURCE_DIR}/*.c"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.cpp"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.cxx"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.h"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.hpp"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.hxx"
		"${CMAKE_CURRENT_SOURCE_DIR}/*.inl"
		"${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_sdlrenderer3.h"
		"${CMAKE_CURRENT_SOURCE_DIR}/backends/imgui_impl_sdlrenderer3.cpp"
)
add_library(${LIBRARY_NAME} STATIC ${BBRX_CMAKE_CURRENT_SOURCES})
bbrx_group_current_sources()
target_include_directories(${LIBRARY_NAME} PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

bbrx_configure_target(${LIBRARY_NAME})

message(STATUS "Added external library: ${LIBRARY_NAME}")

target_include_directories(${LIBRARY_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/External/SDL/include)