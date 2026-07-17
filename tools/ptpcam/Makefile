CC=gcc
# -Wall -Wextra catch common bugs; -Wno-unused-parameter reduces noise from
# the many PTPParams* params that are passed but only used in some paths.
CFLAGS=-Wall -Wextra -Wno-unused-parameter $(shell pkg-config --cflags libusb-1.0)
LDFLAGS=$(shell pkg-config --libs libusb-1.0)

ifeq ($(OS),Windows_NT)
LDFLAGS += -lws2_32
endif

all: ptpcam

clean:
	-rm ptpcam

ptpcam: config.h libptp-endian.h libptp-stdint.h properties.c ptp-pack.c ptp.c ptp.h ptpcam.c ptpcam.h
	$(CC) -o ptpcam properties.c ptp.c ptpcam.c $(CFLAGS) $(LDFLAGS)
