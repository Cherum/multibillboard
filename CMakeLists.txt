cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(Multibillboard)

set(CMAKE_AUTOMOC TRUE)

SET(CMAKE_PREFIX_PATH C:/Qt/5.2.1_msvc2010_opengl/5.2.1/msvc2010_opengl)	
find_package(Qt5 REQUIRED Core Concurrent Declarative Gui Network OpenGL Script Sql Test Xml XmlPatterns Widgets 3D 3DQuick Qml Quick)
find_package(OpenGL)

INCLUDE_DIRECTORIES(
	src
)

set(BILLBOARD_SOURCE
	src/customeffect.cpp
	src/customeffect.h
	src/databundle.cpp
	src/databundle.h
	src/datasource.cpp
	src/datasource.h
	src/multibillboard.cpp
	src/multibillboard.h
	src/multibillboardmodule.cpp
	src/multibillboardmodule.h
)
add_library(MULTIBILLBOARD_LIBRARY STATIC ${BILLBOARD_SOURCE})

TARGET_LINK_LIBRARIES(MULTIBILLBOARD_LIBRARY
	Qt5::Declarative
	Qt5::Script
	Qt5::Xml
	Qt5::OpenGL
	Qt5::Widgets
	Qt5::Gui
	Qt5::Core
	Qt5::3D
	Qt5::3DQuick
	Qt5::Qml
	Qt5::Quick
	
	${OPENGL_LIBRARIES}
)