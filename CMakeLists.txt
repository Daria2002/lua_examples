cmake_minimum_required(VERSION 3.10)

project(luatraining)

file(GLOB_RECURSE luatraining_SOURCES src/*.cpp )
file(GLOB_RECURSE luatraining_HEADERS include/*.hpp)

foreach( testsourcefile ${luatraining_SOURCES} )

    get_filename_component(testname ${testsourcefile} NAME)
    string( REPLACE ".cpp" "" testname ${testname} )

    add_executable(${testname} ${testsourcefile})
    target_compile_features(${testname} PRIVATE cxx_std_17)

    target_link_libraries(${testname} lua dl)

endforeach( testsourcefile ${lua_SOURCES} ) 