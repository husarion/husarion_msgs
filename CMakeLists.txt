cmake_minimum_required(VERSION 2.8.3)
project(husarion_msgs)

find_package(catkin REQUIRED COMPONENTS message_generation std_msgs)

add_message_files(
    DIRECTORY msg
    FILES
    LEDAnimation.msg
    LEDAnimationArr.msg
    PantherDriverStatus.msg
)

add_service_files(
    DIRECTORY srv
    FILES
    LEDBrightness.srv
    LEDPanel.srv
    LEDAnimationId.srv
    LEDSetImageAnimation.srv
)
  
generate_messages(
    DEPENDENCIES
    std_msgs
)

catkin_package(
    CATKIN_DEPENDS std_msgs
)

install(PROGRAMS
   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)