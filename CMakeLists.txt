PROJECT(pvr.vuplus)

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

ENABLE_LANGUAGE(CXX)

FIND_PACKAGE(xbmc REQUIRED)
FIND_PACKAGE(xbmcplatform REQUIRED)
FIND_PACKAGE(TinyXML REQUIRED)

addon_version(pvr.vuplus VUPLUS)

INCLUDE_DIRECTORIES(${xbmcplatform_INCLUDE_DIRS}
                    ${TINYXML_INCLUDE_DIR}
                    ${XBMC_INCLUDE_DIR})

SET(SOURCES src/client.cpp
            src/VuData.cpp)

SET(DEPLIBS ${xbmcplatform_LIBRARIES}
            ${TINYXML_LIBRARIES})

build_addon(pvr.vuplus SOURCES DEPLIBS VUPLUS_VERSION)
install_addon(pvr.vuplus ${VUPLUS_VERSION})
