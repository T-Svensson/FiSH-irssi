ADD_LIBRARY(fish MODULE base64.c blowfish.c inifile.c DH1080.c FiSH.c password.c)
TARGET_LINK_LIBRARIES(fish crypto glib-2.0)

if (APPLE)
	SET_TARGET_PROPERTIES(fish PROPERTIES LINK_FLAGS "-undefined dynamic_lookup")
endif()

INSTALL(TARGETS fish LIBRARY DESTINATION lib/irssi/modules)
