cmake_minimum_required(VERSION 3.26)
GETCURRENTFOLDER()

project(${current_folder})
include_directories(${CRABNETHEADERFILES} ./)
add_executable(${current_folder} DirectoryDeltaTransferTest.cpp readme.txt)
target_link_libraries(${current_folder} ${CRABNET_COMMON_LIBS})
set_target_properties(${current_folder} PROPERTIES PROJECT_GROUP Samples)






