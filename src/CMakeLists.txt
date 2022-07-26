# CMakeList.txt : CMake project for main, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.8)

# Add source to this project's executable.

add_executable (main WIN32 "main.cpp")
find_package(wxWidgets REQUIRED)
target_compile_definitions(main PRIVATE ${wxWidgets_DEFINITIONS} "$<$<CONFIG:DEBUG>:${wxWidgets_DEFINITIONS_DEBUG}>")
target_include_directories(main PRIVATE ${wxWidgets_INCLUDE_DIRS})
target_link_libraries(main PRIVATE ${wxWidgets_LIBRARIES})



if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET main PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
