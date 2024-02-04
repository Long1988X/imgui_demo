cmake_minimum_required(VERSION 3.1...3.28)

project(example_glfw_opengl3)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

message( STATUS "OPENGL_FOUND            = ${OPENGL_FOUND}" )
message( STATUS "OPENGL_XMESA_FOUND      = ${OPENGL_XMESA_FOUND}" )
message( STATUS "OPENGL_GLU_FOUND        = ${OPENGL_GLU_FOUND}" )
message( STATUS "OpenGL_OpenGL_FOUND     = ${OpenGL_OpenGL_FOUND}" )
message( STATUS "OpenGL_GLX_FOUND        = ${OpenGL_GLX_FOUND}" )
message( STATUS "OpenGL_EGL_FOUND        = ${OpenGL_EGL_FOUND}" )
message( STATUS "OPENGL_INCLUDE_DIR      = ${OPENGL_INCLUDE_DIR}" )
message( STATUS "OPENGL_EGL_INCLUDE_DIRS = ${OPENGL_EGL_INCLUDE_DIRS}" )
message( STATUS "OPENGL_LIBRARIES        = ${OPENGL_LIBRARIES}" )

file(GLOB IMGUI_HEADER ./imgui/*.h)
file(GLOB IMGUI_SOURCE ./imgui/*.cpp)

set(MY_HEADER_FILES
	${IMGUI_HEADER}
    )

set(MY_SOURCE_FILES
	${IMGUI_SOURCE}
    )

add_executable(example_glfw_opengl3 ../app/demo.cpp ${MY_HEADER_FILES} ${MY_SOURCE_FILES})
target_link_libraries(example_glfw_opengl3 ${OPENGL_LIBRARY} glfw ${CMAKE_DL_LIBS})