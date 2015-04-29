cmake_minimum_required(VERSION 2.8)
project(snow_sim)
SET(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

  find_package(OpenGL)
  #find_package(GLUT)
  #find_package(GLM)
  #find_package(GLEW)
  find_package(GLFW)


INCLUDE_DIRECTORIES(
		${GLFW_INCLUDE_DIR}
		)

set (LINK_LIBS
		${GLFW_LIBRARY}
		${OPENGL_LIBRARIES})
#SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fpermissive")
#SET(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} ")

# Add executables
ADD_EXECUTABLE(snow Vector2f.cpp Shape.cpp PointCloud.cpp Particle.cpp Matrix2f.cpp main.cpp Grid.cpp)		
TARGET_LINK_LIBRARIES(snow	${LINK_LIBS})
