#############################################################################
#
# XviD examples Makefile
#
# $Id: Makefile,v 1.10 2006-10-11 13:52:06 Skal Exp $
#
#############################################################################

include ../build/generic/platform.inc

# is make running into windows?
ifdef SYSTEMROOT
  EXTRALIBS = -lole32 -lavifil32 -lpthread -lm
else
  EXTRALIBS = -lpthread -lc -lm
endif

HDIR    = -I../src
CFLAGS  = -g3 $(ARCHITECTURE) $(BUS) $(ENDIANNESS) $(FEATURES) $(SPECIFIC_CFLAGS)
LDFLAGS = ../build/generic/=build/$(STATIC_LIB) $(EXTRALIBS)

SOURCES= xvid_encraw.c xvid_decraw.c xvid_bench.c
OBJECTS=$(SOURCES:.c=.o)
TESTS=$(SOURCES:.c=)

all: $(TESTS)

xvid_encraw: xvid_encraw.o
	$(CC) -o $@ $< $(LDFLAGS)

xvid_encraw.o: xvid_encraw.c
	$(CC) $(CFLAGS) $(HDIR) -c $<

xvid_decraw: xvid_decraw.o
	$(CC) -o $@ $< $(LDFLAGS)

xvid_decraw.o: xvid_decraw.c
	$(CC) $(CFLAGS) $(HDIR) -c $<

xvid_bench: xvid_bench.o
	$(CC) -o $@ $< $(LDFLAGS)

xvid_bench.o: xvid_bench.c
	$(CC) $(CFLAGS) $(HDIR) -c $<

clean:
	rm -f $(OBJECTS) $(TESTS)
