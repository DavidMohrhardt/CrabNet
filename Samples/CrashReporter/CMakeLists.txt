cmake_minimum_required(VERSION 3.26)

IF (WIN32 AND NOT UNIX)
	GETCURRENTFOLDER()
	STANDARDSUBPROJECTWITHOPTIONS(${current_folder} "" "" "Dbghelp.lib")
ENDIF(WIN32 AND NOT UNIX)






