# Makefile for T1ToFont 
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 07-Nov-94  AMcC         Updated for Black build
#

#
# Component specific options:
#
COMPONENT = T1ToFont
APP       = !${COMPONENT}
RDIR      = Resources
LDIR      = ${RDIR}.${LOCALE}
INSTDIR   = ${INSTDIR}.${APP}

#
# Generic options:
#
CC      = cc
LD      = link
CP      = copy
RM      = remove 
MKDIR   = cdir
SQUEEZE = squeeze
OBJASM  = objasm
WIPE    = -wipe

AFLAGS  = -depend !Depend -stamp -quit -closeexec
CFLAGS  = -depend !Depend -c -fa -wp ${INCLUDES} ${DFLAGS} ${THROWBACK}
CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Include files:
#
INCLUDES = -IC:

#
# Libraries:
#
CLIB = CLib:o.Stubs
RLIB = RISC_OSLIB:o.risc_oslib

OBJS =\
 frontend.o\
 convert.o\
 encoding.o\
 metrics.o\
 type1.o\
 utils.o

FILES =\
 ${LDIR}.!Help\
 ${LDIR}.!Run\
 ${RDIR}.!RunImage\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.Messages\
 ${LDIR}.Templates\
 ${ENCODINGS}

ENCODINGS =\
  Encodings.Greek\
  Encodings.Selwyn\
  Encodings.Sidney\
  Encodings.Sussex\
  Encodings.SysFixed\
  Encodings.SysFixed4\
  Encodings.System\
  Encodings.TeX\
  Encodings.Specials.Accents_Dn\
  Encodings.Specials.Accents_Up\
  Encodings.Specials.Adobe\
  Encodings.Specials.Dummies

#
# Rule patterns:
#
.c.o:;  ${CC} ${CFLAGS} -o $@ $<
.s.o:;  ${OBJASM} ${AFLAGS} -from $< -to $@

#
# Build rules:
#
all: ${FILES}
        @echo ${COMPONENT}: all build complete

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${MKDIR} ${INSTDIR}.Encodings
        ${MKDIR} ${INSTDIR}.Encodings.Specials
        |
        ${CP} ${LDIR}.!Help       ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run        ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage   ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites    ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22  ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages    ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Templates   ${INSTDIR}.Templates  ${CPFLAGS}
        |
        ${CP} Encodings.Greek     ${INSTDIR}.Encodings.Greek     ${CPFLAGS}
        ${CP} Encodings.Selwyn    ${INSTDIR}.Encodings.Selwyn    ${CPFLAGS}
        ${CP} Encodings.Sidney    ${INSTDIR}.Encodings.Sidney    ${CPFLAGS}
        ${CP} Encodings.Sussex    ${INSTDIR}.Encodings.Sussex    ${CPFLAGS}
        ${CP} Encodings.SysFixed  ${INSTDIR}.Encodings.SysFixed  ${CPFLAGS}
        ${CP} Encodings.SysFixed4 ${INSTDIR}.Encodings.SysFixed4 ${CPFLAGS}
        ${CP} Encodings.System    ${INSTDIR}.Encodings.System    ${CPFLAGS}
        ${CP} Encodings.TeX       ${INSTDIR}.Encodings.TeX       ${CPFLAGS}
        ${CP} Encodings.Specials.Accents_Dn ${INSTDIR}.Encodings.Specials.Accents_Dn ${CPFLAGS}
        ${CP} Encodings.Specials.Accents_Up ${INSTDIR}.Encodings.Specials.Accents_Up ${CPFLAGS}
        ${CP} Encodings.Specials.Adobe      ${INSTDIR}.Encodings.Specials.Adobe      ${CPFLAGS}
        ${CP} Encodings.Specials.Dummies    ${INSTDIR}.Encodings.Specials.Dummies    ${CPFLAGS}
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* lr/r
        Access ${INSTDIR}.Encodings /r
        Access ${INSTDIR}.Encodings.* lr/r
        Access ${INSTDIR}.Encodings.Specials /r
        Access ${INSTDIR}.Encodings.Specials.* lr/r
        |
        @echo ${COMPONENT}: installed

clean:
       ${WIPE} o.* ${WFLAGS}
       ${RM} ${RDIR}.!RunImage
       @echo ${COMPONENT}: cleaned

${RDIR}.!RunImage: ${OBJS} ${CLIB} ${RLIB}
        ${LD} -o $@ ${OBJS} ${CLIB} ${RLIB}
        ${SQUEEZE} $@

# Dynamic dependencies:
o.frontend:	c.frontend
o.frontend:	C:h.wimp
o.frontend:	C:h.os
o.frontend:	C:h.kernel
o.frontend:	C:h.sprite
o.frontend:	C:h.wimpt
o.frontend:	C:h.win
o.frontend:	C:h.event
o.frontend:	C:h.menu
o.frontend:	C:h.baricon
o.frontend:	C:h.res
o.frontend:	C:h.resspr
o.frontend:	C:h.menu
o.frontend:	C:h.template
o.frontend:	C:h.dbox
o.frontend:	C:h.werr
o.frontend:	C:h.font
o.frontend:	C:h.drawmod
o.frontend:	C:h.xferrecv
o.frontend:	C:h.visdelay
o.frontend:	C:h.kernel
o.frontend:	C:h.swis
o.frontend:	C:h.msgs
o.frontend:	h.main
o.frontend:	C:h.os
o.frontend:	C:h.bbc
o.frontend:	h.utils
o.frontend:	h.encoding
o.frontend:	h.metrics
o.frontend:	h.encoding
o.frontend:	h.metrics
o.frontend:	h.type1
o.frontend:	h.frontend
o.convert:	c.convert
o.convert:	h.frontend
o.encoding:	c.encoding
o.encoding:	h.main
o.encoding:	C:h.os
o.encoding:	C:h.kernel
o.encoding:	C:h.bbc
o.encoding:	h.utils
o.encoding:	h.encoding
o.encoding:	h.metrics
o.encoding:	h.encoding
o.encoding:	h.metrics
o.encoding:	C:h.kernel
o.encoding:	C:h.msgs
o.metrics:	c.metrics
o.metrics:	h.main
o.metrics:	C:h.os
o.metrics:	C:h.kernel
o.metrics:	C:h.bbc
o.metrics:	h.utils
o.metrics:	h.encoding
o.metrics:	h.metrics
o.metrics:	h.encoding
o.metrics:	h.metrics
o.metrics:	C:h.msgs
o.type1:	c.type1
o.type1:	h.main
o.type1:	C:h.os
o.type1:	C:h.kernel
o.type1:	C:h.bbc
o.type1:	h.utils
o.type1:	h.encoding
o.type1:	h.metrics
o.type1:	h.encoding
o.type1:	h.metrics
o.type1:	h.type1
o.type1:	C:h.ctype
o.type1:	h.remap
o.type1:	C:h.os
o.type1:	C:h.swis
o.type1:	C:h.msgs
o.type1:	C:h.werr
o.utils:	c.utils
o.utils:	C:h.kernel
o.utils:	h.main
o.utils:	C:h.os
o.utils:	C:h.bbc
o.utils:	h.utils
o.utils:	h.encoding
o.utils:	h.metrics
o.utils:	h.encoding
o.utils:	h.metrics
o.utils:	h.type1
o.utils:	h.rescale
o.utils:	h.adb
o.utils:	h.outlines
o.utils:	h.remap
