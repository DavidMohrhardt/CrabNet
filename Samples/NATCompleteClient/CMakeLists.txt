cmake_minimum_required(VERSION 3.26)
GETCURRENTFOLDER()
SET(EXTRALIBS "") #Extra libraries, we have none
#note the .h files are included so they show up in the windows project
FILE(GLOB XML_FILES ${CrabNet_SOURCE_DIR}/DependentExtensions/XML/*.cpp ${CrabNet_SOURCE_DIR}/DependentExtensions/XML/*.h)#grab all files from xml folder and put them in the XML_FILES var
FILE(GLOB UPNP_FILES ${CrabNet_SOURCE_DIR}/DependentExtensions/UPNP/*.cpp UPNP_FILES ${CrabNet_SOURCE_DIR}/DependentExtensions/UPNP/*.h) #grab all files from UPNP folder and put them in the UPNP_FILES var
SET(EXTRASOURCES ${UPNP_FILES} ${XML_FILES}) #set the grabbed files as extra sources
SET(EXTRAINCLUDES ${CrabNet_SOURCE_DIR}/DependentExtensions/XML  UPNP_FILES ${CrabNet_SOURCE_DIR}/DependentExtensions/UPNP)#add the include directories
STANDARDSUBPROJECTWITHOPTIONSSET(${current_folder})
VSUBFOLDER(${current_folder} "Samples/NAT Punchthrough")





