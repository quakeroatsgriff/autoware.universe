cmake_minimum_required(VERSION 3.14)
project(road_segmentation)

find_package(autoware_cmake REQUIRED)
autoware_package()

include_directories(
  SYSTEM
)

ament_auto_add_library(${PROJECT_NAME} SHARED
  src/road_segmentation.cpp
)

rclcpp_components_register_node(${PROJECT_NAME}
  PLUGIN "autoware::traffic_light::RoadSegmentation"
  EXECUTABLE road_segmentation
)

ament_auto_package(INSTALL_TO_SHARE
  launch
  config
)
