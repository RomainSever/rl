find_package(Boost REQUIRED)

if(RL_BUILD_SG_BULLET OR RL_BUILD_SG_ODE OR RL_BUILD_SG_SOLID)
	add_executable(
		rlRrtDemo
		rlRrtDemo.cpp
		${rl_BINARY_DIR}/robotics-library.rc
	)
	
	target_link_libraries(
		rlRrtDemo
		mdl
		plan
		sg
		Boost::headers
	)
endif()
