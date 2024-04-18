project(app)

find_package(SDL2 REQUIRED CONFIG REQUIRED COMPONENTS SDL2)
find_package(SDL2 REQUIRED CONFIG COMPONENTS SDL2main)
find_package(OpenGL REQUIRED)

set(IMGUI_DIR ../thirdparty/imgui/)
include_directories(${IMGUI_DIR} ${IMGUI_DIR}/backends ../thirdparty/imgui/)

add_executable(
  ${PROJECT_NAME}
  main.cpp
  ${IMGUI_DIR}/backends/imgui_impl_sdl2.cpp
  ${IMGUI_DIR}/backends/imgui_impl_opengl3.cpp
  ${IMGUI_DIR}/imgui.cpp
  ${IMGUI_DIR}/imgui_demo.cpp
  ${IMGUI_DIR}/imgui_draw.cpp
  ${IMGUI_DIR}/imgui_tables.cpp
  ${IMGUI_DIR}/imgui_widgets.cpp)
target_link_libraries(${PROJECT_NAME} SDL2::SDL2 OpenGL::GL)
