
CMAKE_MINIMUM_REQUIRED(VERSION 2.6)
PROJECT(timelib)

SET(SOURCES
    src/astro.c
    src/dow.c
    src/interval.c
    src/parse_date.c
    src/parse_iso_intervals.c
    src/parse_tz.c
    src/timelib.c
    src/tm2unixtime.c
    src/unixtime2tm.c)

SET(HEADERS
    src/astro.h
    src/fallbackmap.h
    src/timelib_config.h
    src/timelib.h
    src/timelib_structs.h
    src/timezonedb.h
    src/timezonemap.h
)

ADD_CUSTOM_COMMAND(
    SOURCE ${timelib_SOURCE_DIR}/src/parse_date.re
    OUTPUT ${timelib_BINARY_DIR}/src/parse_date.c
    WORKING_DIRECTORY ${timelib_SOURCE_DIR}
    COMMAND re2c
    ARGS -d -b -o src/parse_date.c
            src/parse_date.re
)

ADD_CUSTOM_COMMAND(
    SOURCE ${timelib_SOURCE_DIR}/src/parse_iso_intervals.re
    OUTPUT ${timelib_BINARY_DIR}/src/parse_iso_intervals.c
    WORKING_DIRECTORY ${timelib_SOURCE_DIR}
    COMMAND re2c
    ARGS -d -b -o src/parse_iso_intervals.c
            src/parse_iso_intervals.re
)

ADD_LIBRARY(timelib STATIC ${SOURCES})

INSTALL(TARGETS timelib
    ARCHIVE DESTINATION lib
)

INSTALL(FILES ${HEADERS}
    DESTINATION include/timelib
)

CONFIGURE_FILE(timelib.pc.in timelib.pc @ONLY)

INSTALL(FILES ${timelib_SOURCE_DIR}/timelib.pc
    DESTINATION lib/pkgconfig)

