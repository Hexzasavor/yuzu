add_executable(tests
    common/bit_field.cpp
    common/bit_utils.cpp
    common/fibers.cpp
    common/multi_level_queue.cpp
    common/param_package.cpp
    common/ring_buffer.cpp
    core/arm/arm_test_common.cpp
    core/arm/arm_test_common.h
    core/core_timing.cpp
    tests.cpp
)

create_target_directory_groups(tests)

target_link_libraries(tests PRIVATE common core)
target_link_libraries(tests PRIVATE ${PLATFORM_LIBRARIES} catch-single-include Threads::Threads)

add_test(NAME tests COMMAND tests)
