# Test_import_std configuration

add_executable(testbed)

set_target_properties(test_import_std PROPERTIES CXX_EXTENSIONS OFF)
target_compile_features(test_import_std PUBLIC ${ENTT_CXX_STD})

target_compile_definitions(
		test_import_std
    PRIVATE
        ENTT_ID_TYPE=${ENTT_ID_TYPE}
        NOMINMAX
)

target_sources(
	test_import_std
	PRIVATE
		test_import_std.cpp
)

target_link_libraries(
    testbed
    PRIVATE
        EnTT::EnTT
        SDL3::SDL3
)

target_include_directories(
    testbed
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
        ${imgui_SOURCE_DIR}
)
