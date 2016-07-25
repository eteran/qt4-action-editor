cmake_minimum_required (VERSION 2.8)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

find_package(Qt4 4.6.0 REQUIRED QtCore QtGui)
include(${QT_USE_FILE})


set(UI_FILES
	ApplicationWindow.ui
	ActionsDialog.ui
)

qt4_wrap_ui(UI_H ${UI_FILES})

set(action_SRCS
	ActionsDialog.cpp
	ApplicationWindow.cpp
	main.cpp
	${RC_SRCS}
	${UI_H}
)

set(action_INCLUDES
	ApplicationWindow.h
	ActionsDialog.h
)

# we put the header files from the include directory here 
# too so automoc can "just work"
add_executable(action ${action_INCLUDES} ${action_SRCS})

target_link_libraries(action ${CAPSTONE_LIBRARIES} Qt4::QtGui)


set(EXECUTABLE_OUTPUT_PATH ${PROJECT_BINARY_DIR})


