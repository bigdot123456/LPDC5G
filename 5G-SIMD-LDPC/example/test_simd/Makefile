# CC = icc
export CC=/usr/local/bin/gcc-9
export CXX=/usr/local/bin/g++-9
export MPICXX=/usr/local/bin/mpicxx-9

PWD = ../..

SRCS = $(wildcard *.c $(PWD)/src/*.c)

OBJS = $(SRCS:.c = .o)

INCLUDES = -I$(PWD)/inc

LIBS = -lm -lpthread -lmkl_rt -fopenmp $(PWD)/lib/*.a

CCFLAGS = -Wall -O3 -march=core-avx512 -std=c99 -g

OUTPUT = main

all:$(OUTPUT)

$(OUTPUT) : $(OBJS)
	$(CC) $^ -o $@ $(INCLUDES) $(LIBS)

%.o : %.c
	$(CC) -c $< $(CCFLAGS)

clean:
	rm -rf main *.o *.txt    #清除中间文件及生成文件

.PHONY:clean
