cmake_minimum_required(VERSION 3.26)
project(LibRPC3)
IF (NOT WIN32 AND UNIX)
	FILE(GLOB ALL_HEADER_SRCS *.h)
	FILE(GLOB ALL_CPP_SRCS *.cpp)
	FINDBOOST()
	include_directories("${Boost_INCLUDE_DIRS}" ${CRABNETHEADERFILES})
	add_library(LibRPC3 STATIC ${ALL_CPP_SRCS} ${ALL_HEADER_SRCS} "${Boost_INCLUDE_DIRS}" "${Boost_INCLUDE_DIRS}/boost")
	target_link_libraries(LibRPC3 ${CRABNET_COMMON_LIBS} ${Boost_LIBRARIES})
ENDIF(NOT WIN32 AND UNIX)



