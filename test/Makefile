CC=g++
CFLAGS=-g -Wall
BUILD_DIR=../build
INCLUDE_DIR=../include
LIBS=-lgtest -lfract -lgtest_main
TESTS:=$(wildcard ./*.cpp) #All cpp files in test directory must be tests

default: run

.cpp.o:
	$(CC) $(CFLAGS) $< -c -o $*.o -I $(INCLUDE_DIR)

test: $(TESTS:.cpp=.o)
	$(CC) -Wl,-rpath=$(BUILD_DIR) -L$(BUILD_DIR) $(LIBS) \
		-I $(INCLUDE_DIR) $^ -o $@

.PHONY: run

run: test
	./test