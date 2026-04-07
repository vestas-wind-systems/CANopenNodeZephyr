# SPDX-License-Identifier: Apache-2.0

if(CONFIG_CANOPENNODE)
  zephyr_library()

  zephyr_include_directories(
    CANopenNode
    CANopenNode/stack
    include
  )

  zephyr_library_sources(
    CANopenNode/CANopen.c
    CANopenNode/stack/CO_Emergency.c
    CANopenNode/stack/CO_HBconsumer.c
    CANopenNode/stack/CO_LSSmaster.c
    CANopenNode/stack/CO_LSSslave.c
    CANopenNode/stack/CO_NMT_Heartbeat.c
    CANopenNode/stack/CO_PDO.c
    CANopenNode/stack/CO_SDO.c
    CANopenNode/stack/CO_SDOmaster.c
    CANopenNode/stack/CO_SYNC.c
    CANopenNode/stack/CO_TIME.c
    CANopenNode/stack/CO_trace.c
    CANopenNode/stack/crc16-ccitt.c
    src/CO_driver.c
  )

  zephyr_library_sources_ifdef(CONFIG_CANOPENNODE_SYNC_THREAD src/canopen_sync.c)
  zephyr_library_sources_ifdef(CONFIG_CANOPENNODE_STORAGE src/canopen_storage.c)
  zephyr_library_sources_ifdef(CONFIG_CANOPENNODE_LEDS src/canopen_leds.c)
  zephyr_library_sources_ifdef(CONFIG_CANOPENNODE_PROGRAM_DOWNLOAD src/canopen_program.c)

endif()
