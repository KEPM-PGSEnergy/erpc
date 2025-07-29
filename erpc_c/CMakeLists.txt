# Defines a static library
# 'STATIC' means the compiled code from these files will be bundled into a .a archive
add_library(erpc_c STATIC
    infra/erpc_arbitrated_client_manager.cpp
    infra/erpc_basic_codec.cpp
    infra/erpc_client_manager.cpp
    infra/erpc_crc16.cpp
    infra/erpc_framed_transport.cpp
    infra/erpc_message_buffer.cpp
    infra/erpc_message_loggers.cpp
    infra/erpc_server.cpp
    infra/erpc_simple_server.cpp
    infra/erpc_transport_arbitrator.cpp
    port/erpc_port_stdlib.cpp
    port/erpc_threading_pthreads.cpp
    port/erpc_serial.cpp
    setup/erpc_arbitrated_client_setup.cpp
    setup/erpc_client_setup.cpp
    setup/erpc_server_setup.cpp
    setup/erpc_setup_serial.cpp
    setup/erpc_setup_mbf_dynamic.cpp
    setup/erpc_setup_rpmsg_linux.cpp
    transports/erpc_inter_thread_buffer_transport.cpp
    transports/erpc_serial_transport.cpp
    transports/erpc_tcp_transport.cpp
    transports/erpc_rpmsg_linux_transport.cpp
)

# Specifies include directories
# 'PUBLIC' means these paths will be inherited by targets that link to 'erpc_c_arbitrated'
target_include_directories(erpc_c PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/config
    ${CMAKE_CURRENT_SOURCE_DIR}/infra
    ${CMAKE_CURRENT_SOURCE_DIR}/port
    ${CMAKE_CURRENT_SOURCE_DIR}/setup
    ${CMAKE_CURRENT_SOURCE_DIR}/transports
    ${CMAKE_SOURCE_DIR}/rpmsg-cpp
)
