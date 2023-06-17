FILE(GLOB_RECURSE app_sources ${CMAKE_SOURCE_DIR}/main/Winamp480x320/*.c*)
# Append the ULP sources
list(APPEND app_sources ${CMAKE_SOURCE_DIR}/main/ui_font_Cubic11.c)

# set(CMAKE_CXX_STANDARD 17)
# set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(components lvgl jpegdec Arduino wear_levelling ESP32-audioI2S TouchLib esp_lcd Arduino_GFX)

idf_component_register(
    SRCS ${app_sources}
    INCLUDE_DIRS "." "Winamp480x320"
    REQUIRES ${components}
)
