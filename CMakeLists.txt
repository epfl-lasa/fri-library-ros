cmake_minimum_required(VERSION 2.4.6)
project(fri_library_ros)

## NEW
include_directories(${CMAKE_CURRENT_BINARY_DIR}) 
message(STATUS "CMAKE_CURRENT_BINARY_DIR:  ${CMAKE_CURRENT_BINARY_DIR}")
message("PROJECT_NAME:  ${PROJECT_NAME}")
message("PROJECT_SOURCE_DIR:  ${PROJECT_SOURCE_DIR}")

catkin_package(
  INCLUDE_DIRS include
  LIBRARIES fri_library_ros
 # CATKIN_DEPENDS 
#  DEPENDS Ode Bullet
)

## NEW
include_directories(include)
FILE(GLOB SRC_FILES src/*.cpp)
add_library(${PROJECT_NAME} ${SRC_FILES})
target_link_libraries(${PROJECT_NAME}  rt)

# set_target_properties(${PROJECT_NAME}  PROPERTIES RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/bin)
# set_target_properties(${PROJECT_NAME}  PROPERTIES LIBRARY_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/lib)






