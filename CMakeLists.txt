cmake_minimum_required (VERSION 2.8)
project(qt4-action-editor CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)
set(CMAKE_AUTORCC ON)

find_package(Qt4 4.6.0 REQUIRED QtGui)
include(${QT_USE_FILE})

add_executable(qt4-action-editor
	ActionsDialog.cpp
	ActionsDialog.h
	ActionsDialog.ui
	ApplicationWindow.cpp
	ApplicationWindow.h
	ApplicationWindow.ui
	main.cpp
)

target_link_libraries(qt4-action-editor
	Qt4::QtGui
)
