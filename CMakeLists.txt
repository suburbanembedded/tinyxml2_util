add_library(tinyxml2_util
	src/tinyxml2_helper.cpp
)

target_include_directories(tinyxml2_util PUBLIC
	include/
)
if(${BUILD_SHARED_LIBS})
	target_link_libraries(tinyxml2_util
		tinyxml2
	)
else(${BUILD_SHARED_LIBS})
        target_link_libraries(tinyxml2_util
                tinyxml2_static
        )
endif(${BUILD_SHARED_LIBS})

if(DEFINED Doxygen::doxygen)
	doxygen_add_docs(tinyxml2_util_docs
		include/
		src/
	)
endif()
