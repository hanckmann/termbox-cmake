IF(TERMBOX_LIB_BUILD_SHARED)
  ADD_DEFINITIONS( -DTERMBOX_DLL )
ENDIF(TERMBOX_LIB_BUILD_SHARED)

ADD_EXECUTABLE(keyboard
               ${CMAKE_CURRENT_LIST_DIR}/keyboard.c
               )

IF(TERMBOX_LIB_BUILD_SHARED)
    TARGET_LINK_LIBRARIES(keyboard termbox_lib)
ELSE(TERMBOX_LIB_BUILD_SHARED)
    TARGET_LINK_LIBRARIES(keyboard termbox_lib_static)
ENDIF(TERMBOX_LIB_BUILD_SHARED)

SET_TARGET_PROPERTIES(keyboard PROPERTIES OUTPUT_NAME keyboard)
