set(INCS ${CMAKE_CURRENT_SOURCE_DIR})
set(INTERFACES ${CMAKE_CURRENT_SOURCE_DIR})
set(DEFS )
file(GLOB SRC *.c *.h)
__add_real_target(png dll SOURCE ${SRC}
			INC ${INCS}
			INTERFACE ${INTERFACES}
			DEF ${DEFS}
			LIB zlib
)