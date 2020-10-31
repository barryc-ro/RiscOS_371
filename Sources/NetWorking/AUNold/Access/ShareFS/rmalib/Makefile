# -*-Text-*-
#
# $Header: /ax/networking:Starling/ShareFS/rmalib/Makefile:networking  1.2  $
# $Source: /ax/networking:Starling/ShareFS/rmalib/Makefile: $
#
# Copyright (c) 1995 Acorn Computers Ltd., Cambridge, England
#
# Makefile for Freeway module
#
# $Log: Makefile,v $
# Revision 1.2  95/01/09  13:43:39  kwelton
# Now use system versions of "kernel.h" and "swis.h", "_swis.h" no longer
# exists - remade dependencies.
# 
# Revision 1.1  95/01/04  19:17:17  kwelton
# Initial revision
# 
# Revision 1.1  95/01/03  19:00:20  kwelton
# Initial revision
# 
#
# Manually adapted for use under RISC iX
#
#LEVEL=          ../../..
#INCLUDES=       ${LEVEL}/include

CC=             cc
AS=             objasm ${ASFLAGS}
LIB=            libfile

CFLAGS=         -c -zM -zps1 -ffah -wd #-Px
ASFLAGS=        -I<Hdr$Dir>.Global.,<Hdr$Dir>.Interface. -Stamp -quit

RM=             remove
WIPE=           -wipe
CPFLAGS=        ~cfr~v
WFLAGS=         ~c~v

CFILES=         ralloc.c rallocd.c roverwr.c

OBJS=           ralloc.o rallocd.o roverwr.o caller.o

#
# Rule patterns
#
.c.o:;      ${CC} -depend !Depend -c ${CFLAGS} -o $@ $<
.s.o:;      ${AS} -depend !Depend ${AFLAGS} $< $@

all:            rmalib.o

rmalib.o:       ${OBJS}
                ${LIB} -co $@ $?

clean:
        ${WIPE} o.* ${WFLAGS}


# Dynamic dependencies:
o.ralloc:	c.ralloc
o.ralloc:	C:h.kernel
o.ralloc:	C:h.swis
o.ralloc:	h.ralloc
o.rallocd:	c.rallocd
o.rallocd:	C:h.kernel
o.rallocd:	C:h.swis
o.rallocd:	h.ralloc
o.roverwr:	c.roverwr
o.roverwr:	C:h.kernel
o.roverwr:	C:h.swis
o.roverwr:	h.ralloc
o.caller: s.caller
