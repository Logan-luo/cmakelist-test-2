find_package(OpenCV REQUIRED)
aux_source_directory(src Lib_b1)
add_library(assembly2 SHARED ${Lib_b1})
target_include_directories(
    assembly2 PUBLIC include
    ${OpenCV_INCLUDE_DIRS}
)
target_link_libraries(assembly2
    ${OpenCV_LIBS}
)
