#
# Dependencies
#
find_package(Threads)
find_package(wxWidgets REQUIRED)


#
# Sources
#
set(SOURCES
    main.cpp
)



source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SOURCES})


#
# Target
#
add_executable(client WIN32 ${SOURCES})


# Add source to this project's executable.
target_compile_definitions(client PRIVATE ${wxWidgets_DEFINITIONS} "$<$<CONFIG:DEBUG>:${wxWidgets_DEFINITIONS_DEBUG}>")
target_include_directories(client PRIVATE ${wxWidgets_INCLUDE_DIRS})
target_link_libraries(client PRIVATE ${wxWidgets_LIBRARIES})
target_link_libraries(client PRIVATE myproto)
