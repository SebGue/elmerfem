INCLUDE(test_macros)
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

CONFIGURE_FILE( map.sif map.sif COPYONLY)

file(COPY ELMERSOLVER_STARTINFO box.grd  DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

ADD_ELMER_TEST(SD_structmap_p2 LABELS matc quick useextrude serendipity)
