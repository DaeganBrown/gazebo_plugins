cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

# add_library(hello_world SHARED hello_world.cc)
# target_link_libraries(hello_world ${GAZEBO_LIBRARIES})

add_library(velocity_control SHARED velocity_control.cc)
target_link_libraries(velocity_control ${GAZEBO_LIBRARIES})

add_library(target_factory SHARED target_factory.cc)
target_link_libraries(target_factory
  ${GAZEBO_LIBRARIES}
)