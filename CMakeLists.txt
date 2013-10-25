cmake_minimum_required( VERSION 2.6 )

if (NOT CMAKE_BUILD_TYPE)
    set ( CMAKE_BUILD_TYPE Release )
endif (NOT CMAKE_BUILD_TYPE)

add_definitions ( -Wall )
find_package ( Qt4 4.6.0 REQUIRED )
find_package ( X11 REQUIRED )
include ( ${QT_USE_FILE} )
include_directories (
        ${QT_QTCORE_INCLUDE_DIR} ${QT_QTGUI_INCLUDE_DIR}
        )

# additional cmake files
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_SOURCE_DIR}/cmake)

include(RazorInstallConfigPath)
add_definitions(-DRAZOR_ETC_XDG_DIRECTORY=\"${RAZOR_ETC_XDG_DIRECTORY}\")
include(RazorLibSuffix)

add_subdirectory(razor-session)
add_subdirectory(razor-config-session)


