set(MYTEST_SOURCE_FILES
        exception.hpp
        program.cpp
        program.hpp
        program_args.hpp
)

add_library(mytest STATIC ${MYTEST_SOURCE_FILES})

set(suffix "$<IF:$<CONFIG:Debug>,d,>")
target_link_libraries(mytest speed${suffix})
