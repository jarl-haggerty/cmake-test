cmake_minimum_required(VERSION 3.16)
project(hello CXX)

include(FetchContent)

# Writes hello.txt with cmd.exe's echo. The redirection is part of the string
# cmd /c runs, so it's one quoted argument (VERBATIM keeps it intact), and
# there's no space before '>' or the file would end with "hello ".
add_custom_command(
  OUTPUT "${CMAKE_SOURCE_DIR}/hello.txt"
  COMMAND cmd /c hello.bat
  WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}"
  COMMENT "Writing hello.txt"
  VERBATIM)

# A custom command only runs when something depends on its output.
add_custom_target(hello ALL DEPENDS "${CMAKE_SOURCE_DIR}/hello.txt")

include(boost.cmake)
