set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR})

find_package(GTest REQUIRED)

add_executable(${CMAKE_PROJECT_NAME}_test ${CMAKE_CURRENT_SOURCE_DIR}/test_main.cpp)

target_include_directories(
  ${CMAKE_PROJECT_NAME}_test PRIVATE
  ${CMAKE_SOURCE_DIR}/src/include
  ${CMAKE_CURRENT_SOURCE_DIR}/include
  ${GTEST_INCLUDE_DIRS}
)

target_link_libraries(
  ${CMAKE_PROJECT_NAME}_test PRIVATE
  gtest 
  pthread
)