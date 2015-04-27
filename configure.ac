
AC_PREREQ(2.57)

AC_INIT([libhello], [1.0], [lpabon@redhat.com])
AM_INIT_AUTOMAKE([-Wall -Werror foreign])
AC_GNU_SOURCE
m4_ifdef([AM_PROG_AR], [AM_PROG_AR])
AC_CONFIG_HEADERS(src/config.h)
AC_PROG_CC

# Check if CC is linked to CLANG
AC_MSG_CHECKING([if compiling with clang])
AC_COMPILE_IFELSE(
[AC_LANG_PROGRAM([], [[
#ifndef __clang__
       not clang
#endif
]])],
[CLANG=yes], [CLANG=no])
AC_MSG_RESULT([$CLANG])
AM_CONDITIONAL(CLANG, test "$CLANG" = yes)
AM_CONDITIONAL(GCC, test "$GCC" = yes)   # let the Makefile know if we're gcc

AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)
# Check whether some low-level functions/files are available
AC_HEADER_STDC
AC_CONFIG_FILES([Makefile
                 src/Makefile])
AC_OUTPUT
