project(Lesson1PS)
add_executable(Lesson1PS src/main.cpp)
target_link_libraries(Lesson1PS ${SDL2_LIBRARY})
install(TARGETS Lesson1PS RUNTIME DESTINATION ${BIN_DIR})
