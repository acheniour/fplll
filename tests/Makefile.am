AUTOMAKE_OPTIONS = foreign
TOPSRCDIR = $(srcdir)/../src/
TOPBUILDDIR = $(builddir)/../src/
DEFINES =

include_fpllldir=$(includedir)/fplll

EXTRA_DIST=lattices/dim55_in lattices/example_in lattices/example_svp_in lattices/example_svp_out
PERFPUBLISHERFILE=tests-report.xml
# include TOPBUILDIR for fplll_config.h
AM_CPPFLAGS = -I$(TOPSRCDIR) -I$(TOPBUILDDIR)

STAGEDIR := $(realpath -s $(TOPBUILDDIR)/.libs)
AM_LDFLAGS = -L$(STAGEDIR) -Wl,-rpath,$(STAGEDIR) -lfplll
LDFLAGS = -no-install

TESTS = test_lll test_svp test_bkz

test_lll_SOURCES = test_lll.cpp
test_svp_SOURCES = test_svp.cpp
test_bkz_SOURCES = test_bkz.cpp
# Perfpublisher script interaction - AC 2016/06/09
chmod 777 ./perfpublisher
perfpublisher:
	+./perfpublisher.sh "$(PERFPUBLISHERFILE)" "$(TESTS)" "$(CXX)"
check_PROGRAMS = $(TESTS)
