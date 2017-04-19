#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([FULL-PACKAGE-NAME], [VERSION], [BUG-REPORT-ADDRESS])
AM_INIT_AUTOMAKE
AC_CONFIG_SRCDIR([.])
#AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile])


# Checks for programs.
CC=""
AC_PROG_CC([mpicc])
# Checks for libraries.
# Checks for pthread.
AC_CHECK_LIB([pthread], [main],[PTHREAD=-lpthread],echo "Error:
	     Required library pthread not found. Install it and try again" && exit
	     1)
# Checks for mpi.
AC_CHECK_HEADERS([mpi.h], [AC_CHECK_LIB([mpi], [MPI_Init], [mpi=1])])
if test "$mpi" != 1
then
	 AC_MSG_ERROR([MSH requires MPI libraries])
else
	 CC="mpicc"
	 fi

# Checks for header files.
AC_CHECK_HEADERS([stdlib.h])

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.
AC_FUNC_MALLOC
AC_OUTPUT
