configure_file(rl/version.h.in rl/version.h)
install(FILES ${CMAKE_CURRENT_BINARY_DIR}/rl/version.h DESTINATION ${CMAKE_INSTALL_INCLUDEDIR}/rl-${PROJECT_VERSION}/rl COMPONENT development)

add_subdirectory(rl/std)
list(APPEND TARGETS std)

if(RL_BUILD_MATH)
	add_subdirectory(rl/math)
	list(APPEND TARGETS math)
endif()

if(RL_BUILD_UTIL)
	add_subdirectory(rl/util)
	list(APPEND TARGETS util)
endif()

if(RL_BUILD_UTIL_RTAI)
	add_subdirectory(rl/util/rtai)
	list(APPEND TARGETS util_rtai)
endif()

if(RL_BUILD_UTIL_XENOMAI)
	add_subdirectory(rl/util/xenomai)
	list(APPEND TARGETS util_xenomai)
endif()

if(RL_BUILD_XML)
	add_subdirectory(rl/xml)
	list(APPEND TARGETS xml)
endif()

if(RL_BUILD_KIN)
	add_subdirectory(rl/kin)
	list(APPEND TARGETS kin)
endif()

if(RL_BUILD_MDL)
	add_subdirectory(rl/mdl)
	list(APPEND TARGETS mdl)
endif()

if(RL_BUILD_HAL)
	add_subdirectory(rl/hal)
	list(APPEND TARGETS hal)
endif()

if(RL_BUILD_SG)
	add_subdirectory(rl/sg)
	list(APPEND TARGETS sg)
endif()

if(RL_BUILD_PLAN)
	add_subdirectory(rl/plan)
	list(APPEND TARGETS plan)
endif()

set(TARGETS ${TARGETS} PARENT_SCOPE)
