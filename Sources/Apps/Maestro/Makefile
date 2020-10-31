# Makefile for Maestro
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 05-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Maestro
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

#
# Modules to load before squishing
#
PDRIVER    = <Build$Dir>.Modules.PDriver

# Generic options:
#
AS      = aasm
MKDIR   = cdir
CP      = copy
RM      = remove
SQUISH  = squish
WIPE    = -wipe

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(RDIR).EnsureRMA\
 $(LDIR).Messages\
 $(RDIR).Sprites\
 $(RDIR).Sprites22\
 $(LDIR).Templates

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc}

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${RDIR}.EnsureRMA  ${INSTDIR}.EnsureRMA  ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.Messages   ${CPFLAGS}
        ${CP} ${RDIR}.Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
        ${CP} ${RDIR}.Sprites22  ${INSTDIR}.Sprites22  ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.Templates  ${CPFLAGS}
        Access ${INSTDIR} /r
        Access ${INSTDIR}.* lr/r
        @echo ${COMPONENT}: Application installed {Disc}

clean:
        ${RM} ${RDIR}.!RunImage
        ${RM} ${RDIR}.EnsureRMA
        ${WIPE} crunched.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#
${RDIR}.!RunImage: crunched.!RunImage
        rmensure pdriver rmload ${PDRIVER}
        ${SQUISH} ${SQFLAGS} -from crunched.!RunImage -to $@

crunched.!RunImage: bas.!RunImage
        crunch.!RunImage; BASIC

$(RDIR).EnsureRMA: s.EnsureRMA
        ${AS} ${AFLAGS} -from s.EnsureRMA -to $@
        SetType $@ Utility

#---------------------------------------------------------------------------
# Dynamic dependencies:
Resources.EnsureRMA: Hdr:ListOpts
Resources.EnsureRMA: Hdr:Macros
Resources.EnsureRMA: Hdr:System
Resources.EnsureRMA: Hdr:SWIs
Resources.EnsureRMA: Hdr:CPU.Generic26
Resources.EnsureRMA: Hdr:IO.GenericIO
Resources.EnsureRMA: Hdr:RISCOS
Resources.EnsureRMA: Hdr:ModHand
Resources.EnsureRMA: Hdr:Proc
