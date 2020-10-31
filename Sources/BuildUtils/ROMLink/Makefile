# Makefile for Link Utilities
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 27-Jul-94  AMcC         Created.
#

TOOLSDIR = <Tools$Dir>
#
# Generic options:
#
AS      = aasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
LIBFILE = libfile
MKDIR   = cdir
OBJASM  = objasm
RM      = remove
WIPE    = -wipe

AFLAGS  = -depend !Depend -Stamp -quit
CFLAGS  = -c -depend !Depend ${INCLUDES}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~r~v

#
# Include files
#
INCLUDES = 

#
# Rule patterns
#
.c.o:;    ${CC} ${CFLAGS} -o $@ $<

#
# Libraries
#
CLIB      = CLIB:o.stubs
RLIB      = RISCOSLIB:o.risc_oslib
RSTUBS    = RISCOSLIB:o.rstubs
ROMSTUBS  = RISCOSLIB:o.romstubs
ROMCSTUBS = RISCOSLIB:o.romcstubs

#
# Program specific options:
#
COMPONENT = ROMLinkUtils
UTILS     = xtentries symgen

# Build rules

all: ${UTILS}
        @echo ${COMPONENT}: all built

install: ${UTILS}
        ${CP} symgen    ${TOOLSDIR}.symgen    ${CPFLAGS}
        ${CP} xtentries ${TOOLSDIR}.xtentries ${CPFLAGS}
        @echo ${COMPONENT}: all installed

clean:
        ${WIPE} o.* ${WFLAGS}
        ${RM} xtentries
        ${RM} symgen

xtentries: xtentries.o
        ${LD} -o $@ xtentries.o ${CLIB}

symgen: symgen.o
        ${LD} -o $@ symgen.o ${CLIB}

# Dynamic dependencies:
o.xtentries:	c.xtentries
o.symgen:	c.symgen
