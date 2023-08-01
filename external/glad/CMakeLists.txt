add_library(glad)
add_library(glad::glad ALIAS glad)
target_sources(glad PRIVATE src/gl.c)
target_include_directories(glad PUBLIC include)
