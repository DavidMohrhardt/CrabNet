cmake_minimum_required(VERSION 3.26)
GETCURRENTFOLDER()
FINDIRRLICHT()
IF(WIN32 AND NOT UNIX)
	project(${current_folder})
	FILE(GLOB ALL_CPP_SRCS *.cpp "${CrabNet_SOURCE_DIR}/Samples/PHPDirectoryServer2/PHPDirectoryServer2.cpp")
	FILE(GLOB ALL_HEADER_SRCS *.h "${CrabNet_SOURCE_DIR}/Samples/PHPDirectoryServer2/PHPDirectoryServer2.h")
	FILE(GLOB READMES readme.txt Specification.txt)
	FIXCOMPILEOPTIONS()
	include_directories(${CRABNETHEADERFILES} ./ ${IRRLICHT_INCLUDE_DIR})
	add_executable(${current_folder} WIN32 ${ALL_CPP_SRCS} ${ALL_HEADER_SRCS}  ${READMES})
	target_link_libraries(${current_folder} ${CRABNET_COMMON_LIBS})
	set_target_properties(${current_folder} PROPERTIES PROJECT_GROUP "Samples/3D Demos")
ELSE(WIN32 AND NOT UNIX)
	project(${current_folder})
	FINDIRRKLANG()
	FILE(GLOB ALL_CPP_SRCS *.cpp "${CrabNet_SOURCE_DIR}/Samples/PHPDirectoryServer2/PHPDirectoryServer2.cpp")
	FILE(GLOB ALL_HEADER_SRCS *.h "${CrabNet_SOURCE_DIR}/Samples/PHPDirectoryServer2/PHPDirectoryServer2.h")
	FILE(GLOB READMES readme.txt Specification.txt)
	FIXCOMPILEOPTIONS()
	include_directories(${CRABNETHEADERFILES} ./ ${IRRLICHT_INCLUDE_DIR} ${IRRKLANG_INCLUDE_DIR})
	add_executable(${current_folder} WIN32 ${ALL_CPP_SRCS} ${ALL_HEADER_SRCS}  ${READMES})
	target_link_libraries(${current_folder} ${CRABNET_COMMON_LIBS} ${IRRLICHT_LIBRARIES} ${IRRKLANG_LIBRARIES})
ENDIF(WIN32 AND NOT UNIX)






