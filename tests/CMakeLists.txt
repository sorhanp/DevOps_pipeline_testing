set(UNIT_TEST_LIST
  string_utils)

message("Going through the sources:")  
foreach(NAME IN LISTS UNIT_TEST_LIST)
  message(${NAME})
  list(APPEND UNIT_TEST_SOURCE_LIST ${NAME}.test.cpp)
endforeach()

message("\n")

message("The test files are as follows: \n")  
foreach(NAME IN LISTS UNIT_TEST_SOURCE_LIST)
  message(${NAME})
endforeach()

set(TARGET_NAME tests)
 
add_executable(${TARGET_NAME}
  main.cpp
  ${UNIT_TEST_SOURCE_LIST})
 
target_link_libraries(${TARGET_NAME}
  PUBLIC string_utils)
 
target_include_directories(${TARGET_NAME}
  PUBLIC ../externals/catch2/)
 
add_test(
  NAME ${TARGET_NAME}
  COMMAND ${TARGET_NAME} -o report.xml -r junit)