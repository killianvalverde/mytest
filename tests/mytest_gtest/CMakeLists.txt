project(mytest_test)

include_directories(${PROJECT_SOURCE_DIR}/../../src)

set(GTEST_LIBRARIES gtest gtest_main)

set(MYTEST_TEST_SOURCE_FILES
        program_test.cpp
)

add_executable(mytest_test
        main.cpp
        ${MYTEST_TEST_SOURCE_FILES}
)

target_link_libraries(mytest_test mytest ${GTEST_LIBRARIES})
