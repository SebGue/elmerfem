IF(HAVE_UMFPACK OR HAVE_MUMPS)
  INCLUDE(test_macros)
  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

  CONFIGURE_FILE( case.sif case.sif COPYONLY)

  file(COPY mesh.elements mesh.nodes ELMERSOLVER_STARTINFO mesh.header egproject.xml angle.grd mesh.boundary DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

  ADD_ELMER_TEST(periodic_rot LABELS quick n-t)
ENDIF()
