cmake_minimum_required(VERSION 3.5)
project(my_ros2_package)

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclcpp REQUIRED)
find_package(std_msgs REQUIRED)

add_executable(minimal_publisher src/minimal_publisher.cpp)
ament_target_dependencies(minimal_publisher rclcpp std_msgs)
install(TARGETS
  minimal_publisher
  DESTINATION lib/${PROJECT_NAME})

ament_package()

