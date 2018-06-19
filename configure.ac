
AC_PREREQ([2.69])
AC_INIT([timelib], [1], [])
AC_CONFIG_SRCDIR([src/timelib.c])
AC_CONFIG_HEADERS([src/timelib_config.h])
AC_CONFIG_FILES([timelib.pc])
AM_INIT_AUTOMAKE([-Wall -Werror foreign subdir-objects])

AC_PROG_CC
AC_PROG_RANLIB
AM_PROG_AR

sinclude(src/timelib.m4)

AC_TIMELIB_C_BIGENDIAN

AC_CONFIG_FILES([Makefile])
AC_OUTPUT

