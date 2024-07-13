if (CONFIG_HAS_ALTERA_HAL) 
  #nios2 core/system level headers
  zephyr_include_directories(
    include
    altera_hal/HAL/inc
    )

  zephyr_compile_definitions(ZEPHYR_RTOS)
  add_subdirectory(altera_hal/HAL/src)

  if(CONFIG_ALTERA_AVALON_TIMER)
    zephyr_include_directories(
      drivers/altera_avalon_timer/inc
      drivers/altera_avalon_timer/HAL/inc
      )
    add_subdirectory(drivers/altera_avalon_timer/HAL/src)
  endif()

  if(CONFIG_ALTERA_AVALON_SYSID)
    zephyr_include_directories(
      drivers/altera_avalon_sysid/inc
      drivers/altera_avalon_sysid/HAL/inc
      )
    add_subdirectory(drivers/altera_avalon_sysid/HAL/src)
  endif()

  if(CONFIG_ALTERA_AVALON_MSGDMA)
    zephyr_include_directories(
      drivers/altera_msgdma/inc
      drivers/altera_msgdma/HAL/inc
      )
    add_subdirectory(drivers/altera_msgdma/HAL/src)
  endif()

  if(CONFIG_ALTERA_AVALON_I2C)
    zephyr_include_directories(
      drivers/altera_avalon_i2c/inc
      drivers/altera_avalon_i2c/HAL/inc
      )
    add_subdirectory(drivers/altera_avalon_i2c/HAL/src)
  endif()

  if(CONFIG_ALTERA_AVALON_QSPI)
    zephyr_include_directories(
      drivers/altera_generic_qspi_controller2/inc
      drivers/altera_generic_qspi_controller2/HAL/inc
      )
  endif()
endif()
