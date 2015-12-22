
CROSS_COMPILER=../../tools/cross-compiler/gcc-linaro-arm-linux-gnueabihf-4.9/bin/arm-linux-gnueabihf-
CC=$(CROSS_COMPILER)gcc
CFLAGS=-I./include -I./include/libdrm -I../../output/rootfs/usr/local/include -I../../output/rootfs/include
LIBS=-lavformat -lavcodec -lswscale -lavutil -ldl -ldrm -lswresample
LDFLAGS=-L../../output/rootfs/usr/local/lib -L./lib -L../../output/rootfs/lib
C_SRC = $(wildcard *.c)
C_OBJ = $(patsubst %c, %o, $(C_SRC))

.PHONY:all clean
all: ffmpegexample
%o: %c
	@$(CC) $(CFLAGS) -c $<
ffmpegexample:$(C_OBJ)
	@$(CC) -o $@ $^ $(LIBS) $(LDFLAGS)
clean:
	@rm ffmpegexample *.o -f
