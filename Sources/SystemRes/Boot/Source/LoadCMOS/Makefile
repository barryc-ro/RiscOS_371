# Makefile for LoadCMOS
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date           Name       Description
# ----           ----       -----------
# 27th Oct 1994  JC         Created.
#

VPATH = @ <Support$Dir>

#
# Generic options:
#
MKDIR   = cdir
CC      = cc -ISupport: -IOS: -fach -wp
CP      = copy
CPFLAGS = ~cfr~v
OBJASM  = ObjAsm ${THROWBACK} -depend !Depend -stamp -quit
CMHG    = CMHG
LINK    = Link

#
# Libraries:
#
OSLIB  = OSLib:OSLib.o

#
# Program specific options:
#
COMPONENT = LoadCMOS
TARGET    = aof.LoadCMOS

OBJS = o.main o.x

ASMS = s.main s.x

#
# Generic rules {used by top-level build}:
#
export:
        @echo ${COMPONENT}: export complete

clean:
       -Destroy LoadCMOS ${OBJS} ${OBJSD}
        @echo ${COMPONENT}: cleaned

#
# ROM target (re-linked at ROM Image build time)
#
${TARGET}: ${OBJS} ${HFILES} ${OSLIB} ${RSTUBS}
        ${LINK} -o $@ -aof ${OBJS} ${OSLIB} ${RSTUBS}

# Extra {development} rules:
#

all: LoadCMOS
   @Echo Made all

asms: ${ASMS}

release: LoadCMOS
   %Copy LoadCMOS Boot:Library.LoadCMOS ~CFLNRV
   @Echo Made release

#Internal targets
LoadCMOS: ${OBJS} ${OSLIB} CLib:o.Stubs
   ${LINK} -output LoadCMOS ${OBJS} ${OSLIB} CLib:o.Stubs
   Access LoadCMOS WR/R

#General rules
.SUFFIXES: .cmhg .c .debug .o .s

.c.o:
   ${CC} ${THROWBACK} -depend !Depend -c -ff $<

.c.debug:
   ${CC} ${THROWBACK} -depend !Depend -c -DTRACE=1 -o $@ $<

.cmhg.o:
   ${CMHG} $< $@

.c.s:
   ${CC} ${THROWBACK} -depend !Depend -s -ff $<

# Dynamic dependencies:
o.x:	<Support$Dir>.c.x
o.x:	OS:h.kernel
o.x:	OS:h.os
o.x:	OS:h.types
o.x:	<Support$Dir>.h.x
o.main:	c.main
o.main:	OS:h.os
o.main:	OS:h.types
o.main:	OS:h.osbyte
o.main:	OS:h.osfile
o.main:	OS:h.osfind
o.main:	OS:h.osgbpb
o.main:	Support:h.x
