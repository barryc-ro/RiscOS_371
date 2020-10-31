# Makefile for JPEG Compress Module (JCompMod)
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name    Description
# ----       ----    -----------
# 18-Nov-94  GS      Created
# 25-Nov-94  AMcC    Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = JCompMod
MODULE     = rm.${COMPONENT}

#
# Generic options:
#
MKDIR   = cdir
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

CFLAGS  = ${THROWBACK} -c -depend !Depend ${INCLUDES} ${DFLAGS} -zM
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLib:o.stubs
OSLIB     = OSLib:OSLib.o

INCLUDES   = -IOS:
DFLAGS     = -DHAVE_BOOLEAN

OBJS =\
 o.header\
 o.jcapi\
 o.jccoefct\
 o.jccolor\
 o.jcdctmgr\
 o.jcmainct\
 o.jcmarker\
 o.jcomapi\
 o.jcompmod\
 o.jcprepct\
 o.jcparam\
 o.jcsample\
 o.jchuff\
 o.jcmaster\
 o.jerror\
 o.jfdctint\
 o.jmemdst\
 o.jmemmgr\
 o.jmemnoal\
 o.jutils

OBJS_DEBUG =\
 o.hostfs\
 o.trace

#
# Rule patterns
#
.c.o:;     ${CC} ${CFLAGS} -o $@ $<

#
# Main rules:
#
all: ${MODULE}
        @echo ${COMPONENT}: All built

install: ${MODULE}
        ${CP} ${MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        Access ${INSTDIR}.${COMPONENT} WR/r
        @echo ${COMPONENT}: Installed

clean:
        ${RM} ${MODULE}
        ${WIPE} o.* ${WFLAGS}
        @echo ${COMPONENT}: Cleaned

# Static dependencies:

${MODULE}: ${OBJS} ${CLIB} ${OSLIB}
        ${LD} -o $@ -module ${OBJS} ${CLIB} ${OSLIB}

o.header: cmhg.header
        ${CMHG} -o $@ cmhg.header

# Development rules:

debug: rm.jcompmodD
        @echo ${COMPONENT}: Debugging version built

rm.jcompmodD: ${OBJS} ${OBJS_DEBUG} ${CLIB} ${OSLIB}
        ${LD} -o $@ -module ${OBJS} ${OBJS_DEBUG} ${CLIB} ${OSLIB}

# Dynamic dependencies:
o.trace:	c.trace
o.trace:	OS:h.econet
o.trace:	OS:h.types
o.trace:	OS:h.os
o.trace:	OS:h.os
o.trace:	OS:h.osargs
o.trace:	OS:h.osfile
o.trace:	OS:h.osfind
o.trace:	OS:h.osgbpb
o.trace:	h.hostfs
o.trace:	h.trace
o.jcapi:	c.jcapi
o.jcapi:	h.jinclude
o.jcapi:	h.jconfig
o.jcapi:	h.jpeglib
o.jcapi:	h.jmorecfg
o.jcapi:	h.jpegint
o.jcapi:	h.jerror
o.jccoefct:	c.jccoefct
o.jccoefct:	h.jinclude
o.jccoefct:	h.jconfig
o.jccoefct:	h.jpeglib
o.jccoefct:	h.jmorecfg
o.jccoefct:	h.jpegint
o.jccoefct:	h.jerror
o.jccolor:	c.jccolor
o.jccolor:	h.jinclude
o.jccolor:	h.jconfig
o.jccolor:	h.jpeglib
o.jccolor:	h.jmorecfg
o.jccolor:	h.jpegint
o.jccolor:	h.jerror
o.jcdctmgr:	c.jcdctmgr
o.jcdctmgr:	h.jinclude
o.jcdctmgr:	h.jconfig
o.jcdctmgr:	h.jpeglib
o.jcdctmgr:	h.jmorecfg
o.jcdctmgr:	h.jpegint
o.jcdctmgr:	h.jerror
o.jcdctmgr:	h.jdct
o.jcmainct:	c.jcmainct
o.jcmainct:	h.jinclude
o.jcmainct:	h.jconfig
o.jcmainct:	h.jpeglib
o.jcmainct:	h.jmorecfg
o.jcmainct:	h.jpegint
o.jcmainct:	h.jerror
o.jcmarker:	c.jcmarker
o.jcmarker:	h.jinclude
o.jcmarker:	h.jconfig
o.jcmarker:	h.jpeglib
o.jcmarker:	h.jmorecfg
o.jcmarker:	h.jpegint
o.jcmarker:	h.jerror
o.jcomapi:	c.jcomapi
o.jcomapi:	h.jinclude
o.jcomapi:	h.jconfig
o.jcomapi:	h.jpeglib
o.jcomapi:	h.jmorecfg
o.jcomapi:	h.jpegint
o.jcomapi:	h.jerror
o.jcompmod:	c.jcompmod
o.jcompmod:	C:h.swis
o.jcompmod:	C:h.kernel
o.jcompmod:	C:h.kernel
o.jcompmod:	h.trace
o.jcompmod:	OS:h.os
o.jcompmod:	OS:h.types
o.jcompmod:	h.jpeglib
o.jcompmod:	h.jconfig
o.jcompmod:	h.jmorecfg
o.jcprepct:	c.jcprepct
o.jcprepct:	h.jinclude
o.jcprepct:	h.jconfig
o.jcprepct:	h.jpeglib
o.jcprepct:	h.jmorecfg
o.jcprepct:	h.jpegint
o.jcprepct:	h.jerror
o.jcparam:	c.jcparam
o.jcparam:	h.jinclude
o.jcparam:	h.jconfig
o.jcparam:	h.jpeglib
o.jcparam:	h.jmorecfg
o.jcparam:	h.jpegint
o.jcparam:	h.jerror
o.jcsample:	c.jcsample
o.jcsample:	h.jinclude
o.jcsample:	h.jconfig
o.jcsample:	h.jpeglib
o.jcsample:	h.jmorecfg
o.jcsample:	h.jpegint
o.jcsample:	h.jerror
o.jchuff:	c.jchuff
o.jchuff:	h.jinclude
o.jchuff:	h.jconfig
o.jchuff:	h.jpeglib
o.jchuff:	h.jmorecfg
o.jchuff:	h.jpegint
o.jchuff:	h.jerror
o.jcmaster:	c.jcmaster
o.jcmaster:	h.jinclude
o.jcmaster:	h.jconfig
o.jcmaster:	h.jpeglib
o.jcmaster:	h.jmorecfg
o.jcmaster:	h.jpegint
o.jcmaster:	h.jerror
o.jerror:	c.jerror
o.jerror:	h.jinclude
o.jerror:	h.jconfig
o.jerror:	h.jpeglib
o.jerror:	h.jmorecfg
o.jerror:	h.jversion
o.jerror:	h.jerror
o.jerror:	h.jerror
o.jfdctint:	c.jfdctint
o.jfdctint:	h.jinclude
o.jfdctint:	h.jconfig
o.jfdctint:	h.jpeglib
o.jfdctint:	h.jmorecfg
o.jfdctint:	h.jpegint
o.jfdctint:	h.jerror
o.jfdctint:	h.jdct
o.jmemdst:	c.jmemdst
o.jmemdst:	h.jinclude
o.jmemdst:	h.jconfig
o.jmemdst:	h.jpeglib
o.jmemdst:	h.jmorecfg
o.jmemdst:	h.jerror
o.jmemmgr:	c.jmemmgr
o.jmemmgr:	h.jinclude
o.jmemmgr:	h.jconfig
o.jmemmgr:	h.jpeglib
o.jmemmgr:	h.jmorecfg
o.jmemmgr:	h.jpegint
o.jmemmgr:	h.jerror
o.jmemmgr:	h.jmemsys
o.jmemmgr:	h.jmemmgr
o.jmemnoal:	c.jmemnoal
o.jmemnoal:	h.jinclude
o.jmemnoal:	h.jconfig
o.jmemnoal:	h.jpeglib
o.jmemnoal:	h.jmorecfg
o.jmemnoal:	h.jpegint
o.jmemnoal:	h.jerror
o.jmemnoal:	h.jmemsys
o.jutils:	c.jutils
o.jutils:	h.jinclude
o.jutils:	h.jconfig
o.jutils:	h.jpeglib
o.jutils:	h.jmorecfg
o.jutils:	h.jpegint
o.jutils:	h.jerror
