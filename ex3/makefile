
CC=gcc
CFLAGS=-I.
FLAGS = -Wall -g
OBJECTS_MAIN1 = Main.o
OBJECTS_MAIN2= Main2.o

# $@ - the file on the left side of the :
# $< - the first name in the dependencies list
# $^ - the right side of :

#$(TARGET): $(OBJ) lib.a
#	$(CC) -o $@ $^ $(CFLAGS)
all: isort txtfind

isort:  $(OBJECTS_MAIN1) isort.a
	$(CC) $(FLAGS) -o isort $(OBJECTS_MAIN1) isort.a

txtfind: $(OBJECTS_MAIN2) txtfind.a
	$(CC) $(FLAGS) -o txtfind $(OBJECTS_MAIN2) txtfind.a

isort.o: isort.c isort.h
	$(CC) $(FLAGS) -fPIC -c isort.c

txtfind.o: txtfind.c txtfind.h
	$(CC) $(FLAGS) -fPIC -c txtfind.c

txtfind.a: txtfind.o   # can also add here more objects
	ar rcs $@ $^
isort.a: isort.o   # can also add here more objects
	ar rcs $@ $^
#%.o: %.c $(DEPS)
#	$(CC) -c -o $@ $< $(CFLAGS)

# by convention, it starts with lib and ends with .a


.PHONY: clean all 

clean:
	rm -f *.o *.a isort txtfind