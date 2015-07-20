cmake_minimum_required(VERSION 2.8.3)
project(rosserial_r2p)

find_package(catkin REQUIRED COMPONENTS message_generation)

add_message_files(FILES
                  Adc.msg
                 )

add_service_files(FILES
                  Test.srv
                 )

generate_messages()

catkin_package(
  CATKIN_DEPENDS message_runtime
#  CFG_EXTRAS rosserial_r2p-extras.cmake
)

install(DIRECTORY src/ros_lib
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/src
)

install(PROGRAMS src/rosserial_r2p/make_libraries.py
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

install(DIRECTORY launch
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)

