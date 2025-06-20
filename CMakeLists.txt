cmake_minimum_required(VERSION 3.12)

project(AES)

file(GLOB AES_INCLUDE_FILES "*.h") 
file(GLOB AES_SOURCE_FILES  "*.c") 

include_directories(${AES_INCLUDE_FILES})

add_executable(aestest ${AES_SOURCE_FILES})

add_library(aes SHARED aes.c gmult.c)

set(TARGET_INSTALL_BINDIR "bin")
set(TARGET_INSTALL_LIBDIR "lib")
set(TARGET_INSTALL_INCLUDEDIR "include")

install(TARGETS aes LIBRARY DESTINATION ${TARGET_INSTALL_LIBDIR})
install(FILES ${AES_INCLUDE_FILES} DESTINATION ${TARGET_INSTALL_INCLUDEDIR})
