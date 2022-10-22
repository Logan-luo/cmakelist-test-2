aux_source_directory(src Lib_d1)
add_library(module2 SHARED ${Lib_d1})
target_include_directories(
    module2 
    PUBLIC include
)
target_link_libraries(
    module2
    pthread
)
