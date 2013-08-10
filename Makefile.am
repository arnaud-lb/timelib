
lib_LIBRARIES = libtimelib.a

pkgconfigdir = @libdir@/pkgconfig

pkginclude_HEADERS = \
	src/astro.h \
	src/fallbackmap.h \
	src/timelib_config.h \
	src/timelib.h \
	src/timelib_structs.h \
	src/timezonedb.h \
	src/timezonemap.h

dist_pkgconfig_DATA = \
	timelib.pc

libtimelib_a_SOURCES = \
	src/astro.c \
	src/dow.c \
	src/interval.c \
	src/parse_date.c \
	src/parse_iso_intervals.c \
	src/parse_tz.c \
	src/timelib.c \
	src/tm2unixtime.c \
	src/unixtime2tm.c

