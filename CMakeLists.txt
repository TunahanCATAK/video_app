cmake_minimum_required(VERSION 3.14)
project(video-app C CXX)
set(CMAKE_CXX_STANDARD 14)


add_subdirectory(lib/glfw)


if(APPLE)
  list (APPEND EXTRA_LIBS
        "-framework OpenGL"
  )
endif()


add_executable(video-app src/main.cpp)
target_link_libraries(video-app glfw ${EXTRA_LIBS})
