cmake_minimum_required(VERSION 2.8.3)
project(load_config_msgs)

set(MESSAGE_DEPS
		std_msgs
    )

find_package(catkin REQUIRED 
	COMPONENTS 
		message_generation 
		${MESSAGE_DEPS}
)

add_message_files(
	FILES
		ConfigEnum.msg
		LoadError.msg
)

add_service_files(
	FILES
		LoadConfig.srv
)

generate_messages(
	DEPENDENCIES 
		${MESSAGE_DEPS}
)

catkin_package(
	CATKIN_DEPENDS 
		message_runtime 
		${MESSAGE_DEPS}
)
