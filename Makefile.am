SUBDIRS=src tests
include_fpllldir=$(includedir)/fplll
EXTRA_DIST=README.md tools/reformat.pl tools/reformat_magma.pl tools/plot_gso_dump.py
ACLOCAL_AMFLAGS=-I m4
perfpublisher : tests/perfpublisher

tests/perfpublisher:
	(cd tests; ${MAKE} perfpublisher)

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = fplll.pc
