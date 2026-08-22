file(GLOB_RECURSE SRC_FILES "*.c")

set(DRIVER_REQ "driver")
if(IDF_VERSION_MAJOR GREATER_EQUAL 6)
    list(APPEND DRIVER_REQ "esp_driver_ledc")
endif()

idf_component_register(SRCS ${SRC_FILES}
                    INCLUDE_DIRS "."
                    REQUIRES "esp_lcd" ${DRIVER_REQ} "esp_adc" "esp_lcd_jd9853" "esp_lcd_touch_axs5106"  "fatfs" "nvs_flash" "lwip" "esp_wifi")
