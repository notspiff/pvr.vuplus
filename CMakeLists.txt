project(pvr.vuplus)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(xbmc REQUIRED)
find_package(xbmcplatform REQUIRED)
find_package(TinyXML REQUIRED)

include_directories(${xbmcplatform_INCLUDE_DIRS}
                    ${TINYXML_INCLUDE_DIR}
                    ${XBMC_INCLUDE_DIR})

set(VUPLUS_SOURCES src/client.cpp
                   src/VuData.cpp)

set(DEPLIBS ${xbmcplatform_LIBRARIES}
            ${TINYXML_LIBRARIES})

build_addon(pvr.vuplus VUPLUS DEPLIBS)

include(CPack)
