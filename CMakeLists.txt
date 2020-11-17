# Copyright (c) 2020 ARM Limited. All rights reserved.
# SPDX-License-Identifier: Apache-2.0

add_library(mbed-cryptoauthlib INTERFACE)

add_subdirectory(cryptoauthlib)

target_include_directories(mbed-cryptoauthlib
    INTERFACE
        .
        source
        mbed-cryptoauthlib
        cryptoauthlib
        cryptoauthlib/lib
        cryptoauthlib/lib/basic
        cryptoauthlib/lib/hal

)

target_sources(mbed-cryptoauthlib
    INTERFACE
        cryptoauthlib/lib/basic/atca_helpers.c
        source/hal_mbed.cpp
)

target_link_libraries(mbed-cryptoauthlib
    INTERFACE
        cryptoauth
)
