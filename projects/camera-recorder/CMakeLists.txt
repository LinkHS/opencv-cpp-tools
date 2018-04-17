project(camera-recorder)

set(SOURCE main.cpp)

include_directories(${OPENCV_INC_PATH})

link_directories(${OPENCV_LIB_PATH})

add_executable(${PROJECT_NAME} ${SOURCE})

foreach (lib ${OPENCV_LIBS})
  target_link_libraries(${PROJECT_NAME} debug ${lib}d optimized ${lib})
  message("link ${lib}d")
endforeach ()