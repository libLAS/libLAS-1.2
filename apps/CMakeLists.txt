# $Id$
#
# Build libLAS utility programs
#
INCLUDE_DIRECTORIES(
    .
    ../include
    ../include/liblas/capi
)

SET( LASINFO lasinfo )
SET( LAS2LAS las2las )
SET( LAS2TXT las2txt )
SET( TXT2LAS txt2las )
SET( LASMERGE lasmerge )

SET( LASINFO_SRC lascommon.c ${LASINFO}.c )
SET( LAS2LAS_SRC lascommon.c ${LAS2LAS}.c )
SET( LAS2TXT_SRC lascommon.c ${LAS2TXT}.c)
SET( TXT2LAS_SRC lascommon.c ${TXT2LAS}.c )
SET( LASMERGE_SRC lascommon.c ${LASMERGE}.c )

ADD_EXECUTABLE( ${LASINFO} ${LASINFO_SRC} )
ADD_EXECUTABLE( ${LAS2LAS} ${LAS2LAS_SRC} )
ADD_EXECUTABLE( ${LAS2TXT} ${LAS2TXT_SRC} )
ADD_EXECUTABLE( ${TXT2LAS} ${TXT2LAS_SRC} )
ADD_EXECUTABLE( ${LASMERGE} ${LASMERGE_SRC} )

TARGET_LINK_LIBRARIES( ${LASINFO} ${LIBLAS_C_LIB_NAME} )
TARGET_LINK_LIBRARIES( ${LAS2LAS} ${LIBLAS_C_LIB_NAME} )
TARGET_LINK_LIBRARIES( ${LAS2TXT} ${LIBLAS_C_LIB_NAME} )
TARGET_LINK_LIBRARIES( ${TXT2LAS} ${LIBLAS_C_LIB_NAME} )
TARGET_LINK_LIBRARIES( ${LASMERGE} ${LIBLAS_C_LIB_NAME} )
