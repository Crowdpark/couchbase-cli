# Generate the python wrappers
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/couchbase-cli)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbbackup)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbrestore)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbtransfer)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbclusterstats)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbworkloadgen)
CONFIGURE_FILE (${CMAKE_CURRENT_SOURCE_DIR}/wrapper/wrapper.cmake.in
                ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbrecovery)

INSTALL(PROGRAMS
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/couchbase-cli
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbbackup
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbrestore
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbtransfer
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbclusterstats
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbworkloadgen
        ${CMAKE_CURRENT_BINARY_DIR}/wrapper/cbrecovery
        DESTINATION bin)

INSTALL(PROGRAMS
        couchbase-cli
        cbbackup
        cbrestore
        cbtransfer
        cbclusterstats
        cbworkloadgen
        cbrecovery
        DESTINATION lib/python)

INSTALL(FILES
        buckets.py
        cb_bin_client.py
        cbcollections.py
        cbqueue.py
        cluster_stats.py
        collector.py
        couchbaseConstants.py
        diskqueue_stats.py
        info.py
        listservers.py
        node.py
        node_stats.py
        processor.py
        pump.py
        pump_bfd.py
        pump_bson.py
        pump_cb.py
        pump_csv.py
        pump_gen.py
        pump_mbf.py
        pump_mc.py
        pump_sfd.py
        pump_tap.py
        pump_transfer.py
        restclient.py
        stats_buffer.py
        timeout.py
        usage.py
        util_cli.py
        xdcr.py
        DESTINATION lib/python)

INSTALL(FILES
        simplejson/LICENSE.txt
        simplejson/__init__.py
        simplejson/decoder.py
        simplejson/encoder.py
        simplejson/scanner.py
        DESTINATION lib/python/simplejson)
