cmake_minimum_required(VERSION 3.8)
project(humanoid_robot_intelligence_control_system_offset_tuner_msgs)


if($ENV{ROS_VERSION} EQUAL 1)
  find_package(
    catkin REQUIRED COMPONENTS
    std_msgs
    message_generation
  )
else()
  find_package(ament_cmake REQUIRED)
endif()


add_message_files(
  FILES
  JointOffsetData.msg
  JointOffsetPositionData.msg
  JointTorqueOnOff.msg
  JointTorqueOnOffArray.msg
)

add_service_files(
  FILES
  GetPresentJointOffsetData.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
)


if($ENV{ROS_VERSION} EQUAL 1)
  catkin_package(
    CATKIN_DEPENDS
    std_msgs
    message_runtime
  )
endif()
