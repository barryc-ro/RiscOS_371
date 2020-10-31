# Makefile for System
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date           Name   Description
# ----           ----   -----------
# 08-Nov-94      AMcC Updated for Black build
# 15th Nov 1994  JRC  Added SysPaths utility, replaced old 'abs' and 'rm'
#                     directories with a 'Modules' drectory. New 'abs'
#                     directory used to build SysPaths in
# 30-Jan-95      AMcC No longer installs 'recent' modules in 'Modules'
#                     Installs 360.Modules
# 31-Jan-95      AMcC No longer installs !Sprites23. Modules writable by owner
#
# 03-Jul-96      KJB  Added 370 directory

VPATH = @ <Support$Dir>

#
# Program specific options:
#
COMPONENT  = System
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
AS      = objasm
ATTR    = -Attr
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
SQUEEZE = squeeze
WIPE    = -wipe

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit
CFLAGS  = ${THROWBACK} -c -depend !Depend -fah ${INCLUDES} ${DFLAGS} -wp
CPFLAGS = ~cfr~v
SQFLAGS = -f
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLib:o.Stubs
OSLIB     = OSLib:o.OSLib

#
# Include files
#
INCLUDES  = -ISupport:,OS:

MODULES = \
      200.Modules.CLib \
      200.Modules.Colours \
      200.Modules.FPEmulator \
      300.Modules.BASIC64 \
      300.Modules.SCSIFiler \
      300.Modules.SerialUtil \
      310.Modules.Colours \
      310.Modules.ABCLib \
      310.Modules.ABIMod \
      310.Modules.DDEUtils \
      310.Modules.DDT \
      310.Modules.FrontEnd \
      310.Modules.Network.URL.File \
      310.Modules.Network.URL.URL

FILES =\
 ${LDIR}.!Boot\
 ${LDIR}.!Help\
 ${RDIR}.!Run\
 ${RDIR}.!Sprites\
 ${RDIR}.!Sprites22\
 ${MODULES}\
 abs.SysPaths

OBJS = o.main o.x

#
# Rule patterns
#
.SUFFIXES: .oz .od .asm
.c.o:;    ${CC} ${CFLAGS} -ff -o $@ $<
.c.oz:;   ${CC} ${CFLAGS} -ff -zM -zps1 -o $@ $<
.c.od:;   ${CC} ${CFLAGS} -DTRACE=1 -g -o $@ $<
.asm.o:;  ${AS} ${AFLAGS} $< $@
.asm.od:; ${AS} ${AFLAGS} -g $< $@

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${CP} ${LDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} abs.SysPaths       ${INSTDIR}.SysPaths   ${CPFLAGS}
        |
        ${MKDIR} ${INSTDIR}.Modules
        ${MKDIR} ${INSTDIR}.200
        ${MKDIR} ${INSTDIR}.300
        ${MKDIR} ${INSTDIR}.310
        ${MKDIR} ${INSTDIR}.350
        ${MKDIR} ${INSTDIR}.360
        ${MKDIR} ${INSTDIR}.370
        ${CP} 200 ${INSTDIR}.200 ${CPFLAGS}
        ${CP} 300 ${INSTDIR}.300 ${CPFLAGS}
        ${CP} 310 ${INSTDIR}.310 ${CPFLAGS}
        ${CP} 350 ${INSTDIR}.350 ${CPFLAGS}
        ${CP} 360 ${INSTDIR}.360 ${CPFLAGS}
        ${CP} 370 ${INSTDIR}.370 ${CPFLAGS}
        ${CP} Modules ${INSTDIR}.Modules ${CPFLAGS} #shouldn't really be anything in Modules, but SSound currently is
        |
        ${ATTR} -directories +wr ${INSTDIR}
        ${ATTR} -files +ol +or -ow +wr -ww ${INSTDIR}
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.Modules
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.200
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.300
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.310
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.350
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.360
        ${ATTR} -files -ol +or +ow +wr -ww ${INSTDIR}.370
        |
        @echo ${COMPONENT}: All installed (Disc)

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} oz.* ${WFLAGS}
        ${WIPE} od.* ${WFLAGS}
        ${RM} abs.SysPaths
        @echo ${COMPONENT}: cleaned

clean_all:
        Access ${INSTDIR}               rw/
        Access ${INSTDIR}.*             rw/
        Access ${INSTDIR}.200.Modules   rw/
        Access ${INSTDIR}.200.Modules.* rw/
        Access ${INSTDIR}.300.Modules   rw/
        Access ${INSTDIR}.300.Modules.* rw/
        Access ${INSTDIR}.310.Modules   rw/
        Access ${INSTDIR}.310.Modules.* rw/
        Access ${INSTDIR}.350.Modules   rw/
        Access ${INSTDIR}.350.Modules.* rw/
        -Destroy ${OBJS} ${OBJSD} abs.SysPaths ${INSTDIR}.!Boot \
              ${INSTDIR}.!Help ${INSTDIR}.!Run ${INSTDIR}.!Sprites \
              ${INSTDIR}.!Sprites22 ${INSTDIR}.SysPaths
        Wipe ${INSTDIR}.200 ${WFLAGS}R
        Wipe ${INSTDIR}.300 ${WFLAGS}R
        Wipe ${INSTDIR}.310 ${WFLAGS}R
        Wipe ${INSTDIR}.350 ${WFLAGS}R
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
abs.SysPaths: ${OBJS} ${OSLIB} ${CLIB}
        ${LD} -o $@ ${OBJS} ${OSLIB} ${CLIB}
        ${SQUEEZE} ${SQFLAGS} $@

abs.SysPathsD: ${OBJSD} ${OSLIB} ${CLIB}
        ${LD} -o $@ -debug ${OBJSD} ${OSLIB} ${CLIB}

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.main:	c.main
o.main:	OS:h.macros
o.main:	OS:h.os
o.main:	OS:h.types
o.main:	OS:h.osgbpb
o.main:	OS:h.fileswitch
o.main:	Support:h.x
o.x:	<Support$Dir>.c.x
o.x:	C:h.kernel
o.x:	C:h.swis
o.x:	OS:h.macros
o.x:	OS:h.os
o.x:	OS:h.types
o.x:	<Support$Dir>.h.x
