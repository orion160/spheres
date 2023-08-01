cmake_minimum_required(VERSION 3.26)

project(spheres LANGUAGES C CXX)

add_subdirectory(external)

set(SDL2_VERSION 2.28)
set(SDL2_REQUIRED SDL2)
set(SDL2_LINK SDL2::SDL2)

if (WIN32)
	# set(platform WIN32)
	list(APPEND SDL2_REQUIRED SDL2main)
	list(APPEND SDL2_LINK SDL2::SDL2main)
elseif (LINUX)

endif()

find_package(
	SDL2 ${SDL2_VERSION} 
	REQUIRED ${SDL2_REQUIRED}
)

add_executable(spheres ${platform})
target_sources(spheres PRIVATE main.cpp)
target_link_libraries(spheres 
	PRIVATE ${SDL2_LINK} glad::glad
)
