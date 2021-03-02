CC=gcc
CFLAGS=-Wall -g

all: dynamic_block static_block libblock.o libblock.so libstaticblock.a

libblock.o: source/block.c headers/block.h
	$(CC) $(CFLAGS) source/block.c -c source/block.c

libblock.so: source/block.c headers/block.h
	$(CC) $(CFLAGS) -fPIC -shared -o $@ source/block.c -lc

libstaticblock.a: libblock.o
	ar rcs libstaticblock.a block.o

static_block: program.c headers/block.h source/block.c
	$(CC) $(CFLAGS) -o $@ $^ -L. -lstaticblock

static_block1: program.c block.o
	$(CC) $(CFLAGS) -o $@ $^

dynamic_block: program.c headers/block.h source/block.c
	$(CC) $(CFLAGS) -o $@ $^ -L. -lblock

clean:
	rm *.o
