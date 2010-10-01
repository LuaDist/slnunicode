# Copyright (C) 2007-2009 LuaDist.
# Created by Peter Drahoš
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

PROJECT(slnunicode C)
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
INCLUDE(dist.cmake)

ADD_DEFINITIONS(-DluaI_openlib=luaL_openlib) # workaround Lua 5.0 compat

ADD_LUA_MODULE(unicode slnunico.c slnudata.c unicode.def)
ADD_LUA_TEST(unitest)

INSTALL (TARGETS unicode DESTINATION ${INSTALL_CMOD})
INSTALL (FILES unitest DESTINATION ${INSTALL_TEST})
