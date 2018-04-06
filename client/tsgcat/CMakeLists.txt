set(MODULE_NAME "tsgcat")
set(MODULE_PREFIX "FREERDP_CLIENT_TSGCAT")

set(${MODULE_PREFIX}_SRCS tsgcat.c)

add_executable(${MODULE_NAME} ${${MODULE_PREFIX}_SRCS})

set(FREERDP_CLIENT_ENABLED 1)

message(L? ${CMAKE_DL_LIBS})
set(${MODULE_PREFIX}_LIBS ${${MODULE_PREFIX}_LIBS} ${CMAKE_DL_LIBS})
set(${MODULE_PREFIX}_LIBS ${${MODULE_PREFIX}_LIBS} freerdp-client freerdp)
target_link_libraries(${MODULE_NAME} ${${MODULE_PREFIX}_LIBS})

set_property(TARGET ${MODULE_NAME} PROPERTY FOLDER "Client/Sample")
