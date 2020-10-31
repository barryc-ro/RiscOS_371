# Makefile for Fonts
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 08-Nov-94  AMcC   Updated for Black build
# 31-Jan-95  AMcC   !Sprites23 no longer installed
#                   Installation simplified, access attributes set explicitly
# 09-Jun-95  AMcC   MED-05410: !Sprites23 re-instated (temporary fix for
#                   FontMerging.
#

#
# Program specific options:
#
COMPONENT  = Fonts
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
ATTR    = -attr
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

SYSTEM =\
 System.Fixed.f240x120\
 System.Fixed.f240x240\
 System.Fixed.IntMetrics\
 System.Fixed.Outlines\
 System.Medium.IntMetrics\
 System.Medium.Outlines

SELWYN =\
 Selwyn.Encoding\
 Selwyn.IntMetrics\
 Selwyn.Outlines

SIDNEY =\
 Sidney.Encoding\
 Sidney.IntMetrics\
 Sidney.Outlines

NEWHALL =\
 NewHall.Bold.IntMetrics\
 NewHall.Bold.Outlines\
 NewHall.Bold.Italic.IntMetrics\
 NewHall.Bold.Italic.Outlines\
 NewHall.Medium.IntMetrics\
 NewHall.Medium.Outlines\
 NewHall.Medium.Italic.IntMetrics\
 NewHall.Medium.Italic.Outlines

SASSOON =\
 Sassoon.Primary.Intmetric0\
 Sassoon.Primary.Outlines0\
 Sassoon.Primary.Bold.Intmetric0\
 Sassoon.Primary.Bold.Outlines0

FONTS =\
 ${SYSTEM} \
 ${SELWYN} \
 ${SIDNEY} \
 ${NEWHALL} \
 ${SASSOON} \

FILES=\
 ${LDIR}.!Boot\
 ${LDIR}.!Run\
 ${LDIR}.!Sprites\
 ${LDIR}.!Sprites22\
 ${LDIR}.!Sprites23\
 ${LDIR}.!Help\
 ${FONTS}

#
# Main rules:
#
all: ${FILES} ${FONTS}
        @echo ${COMPONENT}: All built (Disc)

install: install_${INSTFLAG}; @

install_all: install_fonts install_app; @

install_app: ${FILES}
        |
        $(MKDIR) $(INSTDIR)
        |
        ${CP} $(LDIR).!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} $(LDIR).!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} $(LDIR).!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} $(LDIR).!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} $(LDIR).!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} $(LDIR).!Sprites23 ${INSTDIR}.!Sprites23 ${CPFLAGS}
        |
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* WR/r
        |
        @echo ${COMPONENT}: Application installed

install_fonts: ${FONTS}
        |
        ${CP} NewHall ${INSTDIR}.NewHall ${CPFLAGS}
        ${CP} Sassoon ${INSTDIR}.Sassoon ${CPFLAGS}
        ${CP} Selwyn  ${INSTDIR}.Selwyn  ${CPFLAGS}
        ${CP} Sidney  ${INSTDIR}.Sidney  ${CPFLAGS}
        ${CP} System  ${INSTDIR}.System  ${CPFLAGS}
        |
        ${ATTR} -directories +wr ${INSTDIR}
        ${ATTR} -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo ${COMPONENT}: Font definitions installed

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
