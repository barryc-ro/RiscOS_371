# Makefile for generating ChangeLogs
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 05-May-95  AMcC         Created.
#

COMPONENT = Releases

#
# The Releases need to be updated as required
#
BASE     = 360
PREVIOUS = 427
CURRENT  = 428

LOGS =\
 ${CURRENT}.ChangeLog\
 ${CURRENT}.NewLog

UTILS =\
 readvers\
 readlogs\
 newlogs\
 mktable

#
# Generic options:
#
CC      = cc
CP      = copy
LD      = link

CFLAGS  = -c -depend !Depend ${INCLUDES}
CPFLAGS = ~cfr~v

#
# Include files
#
INCLUDES = -IC:

#
# Rule patterns
#
.c.o:;    ${CC} ${CFLAGS} -o $@ $<

#
# Libraries
#
CLIB      = CLIB:o.stubs


all: ${CURRENT}.ChangeLog ${CURRENT}.NewLog ${UTILS}
        @echo ${COMPONENT}: all done

${CURRENT}.table: ${BASE}.versions ${PREVIOUS}.versions ${CURRENT}.versions
        mktable ${BASE}.versions ${PREVIOUS}.versions ${CURRENT}.versions $@

${CURRENT}.versions: SrcList
        readvers SrcList $@

#
# Generate the ChangeLogs
#
${CURRENT}.ChangeLog: ${CURRENT}.table
        readlogs ${CURRENT}.table $@

${CURRENT}.NewLog: ${CURRENT}.table
        newlogs ${CURRENT}.table $@

#
# Build the utilities
#
readvers: readvers.o
        ${LD} -o $@ readvers.o ${CLIB}

readlogs: readlogs.o
        ${LD} -o $@ readlogs.o ${CLIB}

mktable: mktable.o
        ${LD} -o $@ mktable.o ${CLIB}

newlogs: newlogs.o
        ${LD} -o $@ newlogs.o ${CLIB}

split: split.o
        ${LD} -o $@ split.o ${CLIB}

csplit: split
        ${CP} split $@ ${CPFLAGS}

join: join.o
        ${LD} -o $@ join.o ${CLIB}
        squeeze $@

# Dynamic dependencies:
o.readvers:	c.readvers
o.mktable:	c.mktable
o.readlogs:	c.readlogs
o.newlogs:	c.newlogs
