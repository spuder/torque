PROG_ROOT = ../..

AM_CFLAGS = -g -DTEST_FUNCTION -I${PROG_ROOT}/ -I${PROG_ROOT}/${PBS_MACH} --coverage -I$(top_srcdir)/src/resmom/@PBS_MACH@ -DPBS_MOM -DDEMUX=\"$(program_prefix)$(DEMUX_PATH)$(program_suffix)\" -DRCP_PATH=\"$(program_prefix)$(RCP_PATH)$(program_suffix)\" -DRCP_ARGS=\"$(RCP_ARGS)\" -DPBS_SERVER_HOME=\"$(PBS_SERVER_HOME)\" -DPBS_ENVIRON=\"$(PBS_ENVIRON)\"

lib_LTLIBRARIES = libtmsock_recov.la

AM_LDFLAGS = @CHECK_LIBS@ ${lib_LTLIBRARIES}

check_PROGRAMS = test_tmsock_recov

libtmsock_recov_la_SOURCES = scaffolding.c ${PROG_ROOT}/tmsock_recov.c
libtmsock_recov_la_LDFLAGS = @CHECK_LIBS@ -shared -lgcov

test_tmsock_recov_SOURCES = test_tmsock_recov.c

check_SCRIPTS = ${PROG_ROOT}/../test/coverage_run.sh

TESTS = $(check_PROGRAMS) ${check_SCRIPTS}

CLEANFILES = *.gcno *.gcda *.gcov core *.lo
