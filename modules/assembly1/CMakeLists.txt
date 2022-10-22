aux_source_directory(src Lib_a1)
aux_source_directory(test Lib_a2)
add_library(assembly1 SHARED ${Lib_a1} ${Lib_a2})
target_include_directories(
    assembly1
    PUBLIC include
)
add_executable(Test test/assembly1_test.cpp)
add_test(NAME assembly1_test COMMAND Test) 
target_link_libraries(
    Test
    assembly1)
