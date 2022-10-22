find_package(OpenCV REQUIRED)
aux_source_directory(src rmath)
add_library(rmath SHARED ${rmath})
target_include_directories(
    rmath
    PUBLIC include ${OpenCV_INCLUDE_DIRS}
)
target_link_libraries(
    rmath
    ${OpenCV_LIBS}
)