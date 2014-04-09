cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

project(MultiBillboard)

set(CMAKE_AUTOMOC TRUE)

set(QT_PATH C:/Qt/5.2.1_msvc2010_opengl/5.2.1/msvc2010_opengl/include)

INCLUDE_DIRECTORIES(
	${QT_PATH}
	${QT_PATH}/QtCore
	${QT_PATH}/QtGui
	${QT_PATH}/Qt3D 
	${QT_PATH}/Qt3DQuick 
	${QT_PATH}/QtQml 
	${QT_PATH}/QtQuick
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
add_library(MultiBillboard STATIC ${BILLBOARD_SOURCE})