
# Author: TheFrenchLeaf https://github.com/TheFrenchLeaf

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

PROJECT(CXSparse C)

INCLUDE_DIRECTORIES(./
./Include)

FILE(GLOB CXSparse_SRCS "Source/*.c")
set_source_files_properties(${CXSparse_SRCS} PROPERTIES LANGUAGE C)
add_definitions(-DNCOMPLEX)

ADD_LIBRARY(cxsparseMVG STATIC ${CXSparse_SRCS})
if(UNIX)
  TARGET_LINK_LIBRARIES(cxsparseMVG m)
  SET_TARGET_PROPERTIES(cxsparseMVG PROPERTIES COMPILE_FLAGS -fPIC)
ENDIF(UNIX)

