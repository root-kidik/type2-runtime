CC            = gcc
CFLAGS        = -std=gnu99 -Os -D_FILE_OFFSET_BITS=64 -DGIT_COMMIT=\"${GIT_COMMIT}\" -T data_sections.ld -ffunction-sections -fdata-sections -Wl,--gc-sections -static -Wall
LIBS          = -lsquashfuse -lsquashfuse_ll -lzstd -lz -lfuse3 -llz4 -llzma -larchive -llzo2 -lpthread -ldl

all: runtime

runtime: runtime.c
	$(CC) -I/usr/local/include/squashfuse -I/usr/include/fuse3 $(CFLAGS) $^ $(LIBS) -o $@

clean:
	rm -f runtime
