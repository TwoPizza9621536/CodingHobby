project(Lesson0PS)
add_executable(Lesson0PS src/main.cpp)
target_link_libraries(Lesson0PS ${SDL2_LIBRARY})
install(TARGETS Lesson0PS RUNTIME DESTINATION ${BIN_DIR})
