# Makefile for BF layer
LIB	= bf
INCDIR	= ${MINIREL_HOME}/h
INCS	= 
SRCS	= ${MINIREL_HOME}/bf/bf.c ${MINIREL_HOME}/bf/hash_table.c ${MINIREL_HOME}/bf/free_list.c ${MINIREL_HOME}/bf/lru.c
TESTS	= bftest.c
OBJS	= ${SRCS:.c=.o}
LIBS	= lib${LIB}.a

#############################################################################
# This macro definition can be overwritten by command-line definitions.
CC	= gcc
CFLAGS	= -g -ansi -pedantic -Wall -Wextra -Werror
#CFLAGS	= -O -ansi -pedantic
#############################################################################

all: lib${LIB}.a ${LIB}test

${LIB}test: ${LIB}test.o lib${LIB}.a
	$(CC) $(CFLAGS) -o $@ $< ${LIBS}

lib${LIB}.a:$(OBJS)
	ar cr lib${LIB}.a $(OBJS)
	ranlib lib${LIB}.a

$(OBJS): ${INCS}

clean:
	rm -f lib${LIB}.a *.o ${LIB}test *.bak *~

.c.o:; $(CC) $(CFLAGS) -c $< -I. -I$(INCDIR)


