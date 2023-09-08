cmake_minimum_required(VERSION 2.8.3)
project(your_ros_package)

## Find catkin and any catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  dynamic_reconfigure  # Add this if using dynamic reconfigure
)

## Declare a catkin package
catkin_package(
  CATKIN_DEPENDS roscpp std_msgs dynamic_reconfigure  # Add any other dependencies here
)

## Build the nodes
include_directories(
  ${catkin_INCLUDE_DIRS}
)

## Add your executable node(s)
add_executable(your_driver_node src/your_driver_node.cpp)  # Replace with your source file
target_link_libraries(your_driver_node ${catkin_LIBRARIES})

## Add any other executables or libraries if needed

## Install rules
install(TARGETS
  your_driver_node
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)
