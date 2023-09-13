cmake_minimum_required(VERSION 3.5)
project(aim_assistant_msgs)

find_package(ament_cmake REQUIRED)
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

file(GLOB ROS2_MSG RELATIVE "${CMAKE_CURRENT_SOURCE_DIR}" "msg/*.msg")

rosidl_generate_interfaces(${PROJECT_NAME} 
    ${ROS2_MSG}
    DEPENDENCIES std_msgs geometry_msgs sensor_msgs
)

ament_package()