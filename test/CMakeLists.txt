enable_testing()

find_package(GTest CONFIG REQUIRED)

add_executable(
  lib_test
  lib_test.cpp
)

target_link_libraries(
  lib_test
  PRIVATE
   GTest::gtest GTest::gtest_main GTest::gmock GTest::gmock_main
)

include(GoogleTest)
gtest_discover_tests(lib_test)