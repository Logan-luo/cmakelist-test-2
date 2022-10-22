cmake_minimum_required(VERSION 3.10)
project(Test)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
# Enable C++17
enable_testing()
# # # # 以下内容禁止修改 # # # #
option(BUILD_A "build modules a" ON)
option(BUILD_B "build modules b" OFF)
option(BUILD_TESTS "build tests" OFF)

if(BUILD_TESTS)
    enable_testing()
endif()

add_subdirectory(modules)
add_subdirectory(common)
# 小提示: module2 需要用到 pthread，即 target_link_libraries(xxx pthread)
# # # # 以上内容禁止修改 # # # #


if (BUILD_A)
    add_compile_definitions(WITH_A)
endif()
if (BUILD_B)
    add_compile_definitions(WITH_B)
endif()




add_executable(client client.cpp)

target_link_libraries(  
    client
    module2)

add_executable(server server.cpp)

target_link_libraries(
    server
    rmath
    module1
    module2
    singleton)



