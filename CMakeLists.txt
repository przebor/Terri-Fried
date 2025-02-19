cmake_minimum_required(VERSION 2.8)

if(NOT DEFINED CMAKE_TOOLCHAIN_FILE)
  if(DEFINED ENV{VITASDK})
    set(CMAKE_TOOLCHAIN_FILE "$ENV{VITASDK}/share/vita.toolchain.cmake" CACHE PATH "toolchain file")
  else()
    message(FATAL_ERROR "Please define VITASDK to point to your SDK path!")
  endif()
endif()

project(Terri-Fried)
include("${VITASDK}/share/vita.cmake" REQUIRED)

set(VITA_APP_NAME "Terri-Fried")
set(SHORT_NAME Terri-Fried)
set(VITA_TITLEID  "PLYMARS01")
set(VITA_VERSION  "01.00")

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Wall")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(VITA_MKSFOEX_FLAGS "${VITA_MKSFOEX_FLAGS} -d PARENTAL_LEVEL=1")

link_directories(
    ${CMAKE_CURRENT_BINARY_DIR}
)

add_executable(${VITA_APP_NAME}
    src/main.cpp
    src/player.h
    src/player.cpp
    src/platform.h
    src/platform.cpp
    src/const.h
)

target_link_libraries(${VITA_APP_NAME}
    SceAppMgr_stub
    c
    debugnet
    SceNetCtl_stub
    SceNet_stub
    SceSysmodule_stub
    SceLibKernel_stub
    SceDisplay_stub
    SceTouch_stub
    SceAudio_stub
    SceAppMgr_stub
    -lvita2d
    -lSceDisplay_stub
    -lSceGxm_stub
    -lSceSysmodule_stub
    -lSceCtrl_stub
    -lScePgf_stub
    -lScePvf_stub
    -lSceCommonDialog_stub
    -lfreetype
    -lpng
    -ljpeg
    -lz
    -lm
    -lc
    soloud
    pthread
    m
)

vita_create_self(${SHORT_NAME}.self ${SHORT_NAME})
vita_create_vpk(${SHORT_NAME}.vpk ${VITA_TITLEID} ${SHORT_NAME}.self
    VERSION ${VITA_VERSION}
    NAME ${VITA_APP_NAME}

    # Livearea files
    FILE sce_sys/ sce_sys/

    # Resources
    FILE resources/ resources/
)

