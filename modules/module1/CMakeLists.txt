find_package(OpenCV REQUIRED)
aux_source_directory(src/module1a Lib_c1)
aux_source_directory(src/module1b Lib_c2)
add_library(module1 SHARED ${Lib_c1} ${Lib_c2})
target_include_directories(
    module1 PUBLIC include
    ${OpenCV_INCLUDE_DIRS}
)
target_link_libraries(module1
    ${OpenCV_LIBS}
    assembly2
)