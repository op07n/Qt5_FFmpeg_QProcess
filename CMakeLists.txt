cmake_minimum_required(VERSION 3.8)

project(Qt5_FFmpeg_QProcess)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/build)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})


set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)


ADD_DEFINITIONS (${QT_DEFINITIONS})



find_package (Qt5 REQUIRED COMPONENTS Widgets Core Gui Network)


INCLUDE_DIRECTORIES(".\\GeneratedFiles")

set(SRCS main.cpp
         dialog.ui
         dialog.h
         dialog.cpp)
	 
set_property(SOURCE UDPListener.cpp PROPERTY SKIP_AUTOMOC ON)	 
         
add_executable(${PROJECT_NAME} ${SRCS})

set_target_properties(${PROJECT_NAME} PROPERTIES
	CXX_STANDARD 17
	CXX_STANDARTD_REQUIRED ON
)


qt5_use_modules(Qt5_FFmpeg_QProcess Widgets Core Gui Network)

# target_link_libraries(${PROJECT_NAME}
#     ${Qt5Core_LIBRARIES}
#     ${Qt5Network_LIBRARIES}
# )
