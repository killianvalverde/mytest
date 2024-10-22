set(MAIN_SOURCE_FILES
        main.cpp
)

add_executable(main ${MAIN_SOURCE_FILES})
target_link_libraries(main mytest)

if(WIN32)
    install(TARGETS main DESTINATION .)
else()
    install(TARGETS main DESTINATION bin)
endif()

set_target_properties(main PROPERTIES OUTPUT_NAME mytest)
