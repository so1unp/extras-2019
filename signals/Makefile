GEN_EXE = intquit ouch

EXE = ${GEN_EXE}

all : ${EXE}

allgen : ${GEN_EXE}

#
# The following example programs make use of signal() (instead of the
# preferred sigaction()) to establish signal handlers.
# By default, signal() on Linux follows the BSD semantics, establishing 
# a reliable signal handler. This is because _BSD_SOURCE is enabled
# bt default in <features.h>. However, in ../Makefile.inc, we define 
# CFLAGS to include _XOPEN_SOURCE, and this has the effect of disabling
# _BSD_SOURCE. To ensure that we get the default (BSD) semantics
# we here explicitly define _BSD_SOURCE when compiling these programs.
#

ouch : ouch.c
	${CC} -o $@ ouch.c ${CFLAGS} ${LDLIBS}

intquit : intquit.c
	${CC} -o $@ intquit.c ${CFLAGS} ${LDLIBS}

clean : 
	${RM} ${EXE} *.o

