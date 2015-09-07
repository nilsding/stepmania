include(CMakeProject-lua.cmake)
if (NOT BSD)
  include(CMakeProject-glew.cmake)
endif()

include(CMakeProject-json.cmake)

if (NOT SYSTEM_PCRE_FOUND)
  include(CMakeProject-pcre.cmake)
endif()

include(CMakeProject-tomcrypt.cmake)
include(CMakeProject-tommath.cmake)

if (APPLE OR MSVC)
  include(CMakeProject-zlib.cmake)
endif()

if (NOT BSD)				#Let BSD link against it's own version of libPNG, 
  include(CMakeProject-png.cmake) 	#because even though the include path is set, it uses the wrong header.
endif()					#Probably fixable inside the source files.

if (APPLE)
  include(CMakeProject-jpeg.cmake)
  include(CMakeProject-mad.cmake)
endif()
