cmake_minimum_required(VERSION 3.2)

project(lb_test)

find_package(Boost REQUIRED COMPONENTS unit_test_framework )

file(GLOB simple "../../src/simple/*.cpp")

file(GLOB src 
    ut_all_or_none.cpp
    ut_bbo_order_book.cpp
    ut_depth.cpp
    ut_immediate_or_cancel.cpp
    #ut_listeners.cpp
    ut_main.cpp
    ut_order_book.cpp
    ut_market_price.cpp
    ut_order_book_shared_ptr.cpp
    #ut_stop_orders.cpp
)

add_executable(lb_test ${src} ${simple})

target_include_directories( lb_test PRIVATE
    ../../src
)

target_link_libraries( lb_test ${Boost_UNIT_TEST_FRAMEWORK_LIBRARY})
