cmake_minimum_required(VERSION 2.8.4)

cmake_policy(SET CMP0048 NEW)
PROJECT(SystemC VERSION 0.01.02 LANGUAGES NONE)

set(MainFile "ISC20_Frankfurt.tex")	# Is used to define output file name
file(GLOB_RECURSE InputFiles RELATIVE "${CMAKE_SOURCE_DIR}" src/*.tex)
set(InputFiles ${MainFile} Main.tex ${InputFiles}
)
### CMake will copy all source files to its own area
### These standard subdirectories are copied by default
# file(COPY "${CMAKE_SOURCE_DIR}/dat" DESTINATION "${CMAKE_BINARY_DIR}")
 file(COPY "${CMAKE_SOURCE_DIR}/lst" DESTINATION "${CMAKE_BINARY_DIR}")
## Copy extra directories or files similarly, if you need
 

### Select language settings
### If you use dual language source, provide here which source follows first and which is the second
### It might change from project to project!
#
set(FirstLanguage "english") # language must be set!
set(SecondLanguage "magyar") # Usual setting language
#
# Choose if you need both languages in batch compilation
#
set(NEED_BOTH_LANGUAGES OFF CACHE BOOL "Make both language versions of the course" OFF)
#
# Choose if to use the second or 1st language, if only one language
#
  set(USE_SECOND_LANGUAGE OFF CACHE BOOL "If to use the 2nd or 1st language" OFF)
#

### General-purpose settings
# Choose whether you need debugging support
#
  set(DEBUG_MODE OFF CACHE BOOL "Include debug support for lecture making" FORCE)
#  option (DEBUG_MODE "Include debug support for lecture making"  ON)
#

### Beamer-related settings
# 
  set(DISABLE_WIDE_SCREEN OFF CACHE BOOL "Use 4:3 screen rather than 16:9" FORCE)
#  option ( DISABLE_WIDE_SCREEN "Use 4:3 screen rather than 16:9" OFF)
  set(DISABLE_TOC OFF CACHE BOOL "Disable table of contents, in Beamer only" FORCE)
#  option ( DISABLE_TOC "Disable table of contents, in Beamer only" OFF)
  set(DISABLE_SECTION_TOC OFF CACHE BOOL "Disable sections in table of contents, in Beamer only" FORCE)
#  option ( DISABLE_SECTION_TOC "Disable sections in table of contents, in Beamer only" OFF)
 
### Output format related settings
#
  set(NEED_FORMAT_BEAMER_ME   ON CACHE BOOL "Generate output in format beamer_ME" FORCE)
#  option ( NEED_FORMAT_BEAMER_ME "Generate output in format beamer_ME " ON)
  set(NEED_FORMAT_MEMOIR_A4FANCY   ON CACHE BOOL "Generate output in format memoir A4Fancy" FORCE)
#  option ( NEED_FORMAT_MEMOIR_A4FANCY ON "Generate output in format memoir A4Fancy " ON)
  set(NEED_FORMAT_MEMOIR_eBook   ON CACHE BOOL "Generate output in format memoir eBook" FORCE)
#  option ( NEED_FORMAT_MEMOIR_eBook "Generate output in format memoir eBook " ON)
  set(NEED_FORMAT_MEMOIR_WEB   ON CACHE BOOL "Generate output in format memoir WEB " FORCE)
#  option ( NEED_FORMAT_MEMOIR_WEB "Generate output in format memoir WEB" ON)

 
###!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
### 
### !! Do not edit below this line until you know what you are doing!!
###
###!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!
# This is the UseLatex macros
include(../../common/UseLATEX.cmake)
include(../../common/MultEdu.cmake)
include(../../common/CleanEdu.cmake)

