cmake_minimum_required(VERSION 2.8.3)
project(sawyer_learning_interface_msgs)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  roscpp
  rospy
  std_msgs
  actionlib
  actionlib_msgs
  message_generation
)


add_message_files(
        FILES
        float1d.msg
)

add_action_files(
        DIRECTORY
        action
        FILES
        PbDLib.action
)

generate_messages(
        DEPENDENCIES
        actionlib_msgs std_msgs
)

include_directories(
        SYSTEM include
        ${catkin_INCLUDE_DIRS}
)

catkin_package(
        CATKIN_DEPENDS actionlib_msgs message_runtime
)
include_directories(
        # include
        ${catkin_INCLUDE_DIRS}
)
