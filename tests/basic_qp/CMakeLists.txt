get_directory_property(OSQP_TESTCASE_SRCS DIRECTORY ${PROJECT_SOURCE_DIR}/tests DEFINITION OSQP_TESTCASE_SRCS)

set(OSQP_TESTCASE_SRCS
    ${OSQP_TESTCASE_SRCS}
    ${CMAKE_CURRENT_SOURCE_DIR}/test_basic_qp.cpp
    ${CMAKE_CURRENT_SOURCE_DIR}/test_later_solution.cpp
    PARENT_SCOPE)

if(OSQP_ALGEBRA_CUDA)
    set(OSQP_TESTCASE_SRCS
        ${OSQP_TESTCASE_SRCS}
        ${CMAKE_CURRENT_SOURCE_DIR}/test_cuda_io.cpp
        PARENT_SCOPE)
endif()

get_directory_property(OSQP_TESTCASE_GENERATED_SRCS DIRECTORY ${PROJECT_SOURCE_DIR}/tests DEFINITION OSQP_TESTCASE_GENERATED_SRCS)

set(OSQP_TESTCASE_GENERATED_SRCS
    ${OSQP_TESTCASE_GENERATED_SRCS}
    ${CMAKE_CURRENT_SOURCE_DIR}/basic_qp_data.cpp
    PARENT_SCOPE)

get_directory_property(OSQP_TESTCASE_GENERATORS DIRECTORY ${PROJECT_SOURCE_DIR}/tests DEFINITION OSQP_TESTCASE_GENERATORS)

set(OSQP_TESTCASE_GENERATORS
    ${OSQP_TESTCASE_GENERATORS}
    ${CMAKE_CURRENT_SOURCE_DIR}/generate_problem.py
    PARENT_SCOPE)

get_directory_property(OSQP_TESTCASE_DIRS DIRECTORY ${PROJECT_SOURCE_DIR}/tests DEFINITION OSQP_TESTCASE_DIRS)

set(OSQP_TESTCASE_DIRS
    ${OSQP_TESTCASE_DIRS}
    ${CMAKE_CURRENT_SOURCE_DIR}
    PARENT_SCOPE)
