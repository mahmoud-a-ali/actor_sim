cmake_minimum_required(VERSION 2.8.3)
project(actor_sim)

find_package(catkin REQUIRED COMPONENTS)

# Gazebo
find_package(gazebo 8 QUIET)
if(NOT gazebo_FOUND)
  find_package(gazebo 9 REQUIRED)
endif()


include_directories(
  ${catkin_INCLUDE_DIRS}
  ${GAZEBO_INCLUDE_DIRS}
)


set(trajectory_actor_plugin_name TrajectoryActorPlugin)
catkin_package(
  CATKIN_DEPENDS
  LIBRARIES ${trajectory_actor_plugin_name}
)



#############################
## Trajectory Actor plugin ##
#############################

# Create the libTrajectoryActorPlugin.so library.
add_library(${trajectory_actor_plugin_name} SHARED
  src/TrajectoryActorPlugin.cc
)
target_link_libraries(${trajectory_actor_plugin_name}
  ${GAZEBO_LIBRARIES}
  ${catkin_LIBRARIES}
)
install(TARGETS ${trajectory_actor_plugin_name}
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_GLOBAL_BIN_DESTINATION}
)


