# Makefile for Chars
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
COMPONENT  = Chars
APP        = !${COMPONENT}
ROM_MODULE = rm.${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources.${COMPONENT}
RESAPP = <resource$dir>.Apps.${APP}

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
SQUISH    = squish
WIPE    = -wipe

AFLAGS  = ${THROWBACK} -depend !Depend -nocache -stamp -quit -module
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES =\
 ${LDIR}.!Help \
 ${RDIR}.!Run \
 ${RDIR}.!RunImage \
 ${LDIR}.Messages \
 ${LDIR}.Templates 

# Resources to be included in the ROM module (not in Messages module}
RESFILES =\
 ${RDIR}.!RunImage

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: Application built (Disc}

rom: ${ROM_MODULE}
        @echo ${COMPONENT}: Module built (ROM}

install: ${FILES}
        ${MKDIR} ${INSTDIR}.${APP}
        |
        ${CP} ${LDIR}.!Help      ${INSTDIR}.${APP}.!Help     ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.${APP}.!Run      ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.${APP}.!RunImage ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.${APP}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${INSTDIR}.${APP}.Templates ${CPFLAGS}
        |
        Access ${INSTDIR}.${APP}.* lr/r
        |
        @echo ${COMPONENT}: Application installed {Disc}

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed {ROM}

resources: ${LDIR}.!RunLink
        ${MKDIR} ${RESAPP}
        ${MKDIR} ${RESDIR}
        |
        ${CP} ${LDIR}.!Help      ${RESAPP}.!Help     ${CPFLAGS}
        ${CP} ${RDIR}.ROM.!Run   ${RESAPP}.!Run      ${CPFLAGS}
        |
        ${CP} ${LDIR}.!RunLink   ${RESDIR}.!RunLink  ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${RESDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${RESDIR}.Templates ${CPFLAGS}
        |
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${RM} ${ROM_MODULE}
        ${RM} ${RDIR}.!RunImage
        ${RM} ${LDIR}.!RunLink
        ${WIPE} crunched.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#

${ROM_MODULE}: s.Main ${RESFILES}
        ${AS} ${AFLAGS} -from s.Main -to $@

${RDIR}.!RunImage: crunched.!RunImage
        ${SQUISH} ${SQFLAGS} -from crunched.!RunImage -to $@

crunched.!RunImage: bas.!RunImage
        crunch.!RunImage; BASIC

${LDIR}.!RunLink: bas.!RunLink
        ${SQUISH} ${SQFLAGS} -from bas.!RunLink -to $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Chars: s.AppName
rm.Chars: Hdr:ListOpts
rm.Chars: Hdr:Macros
rm.Chars: Hdr:System
rm.Chars: Hdr:SWIs
rm.Chars: Hdr:CPU.Generic26
rm.Chars: Hdr:IO.GenericIO
rm.Chars: Hdr:RISCOS
rm.Chars: Hdr:ModHand
rm.Chars: Hdr:Services
rm.Chars: Hdr:Proc
rm.Chars: Hdr:ResourceFS
rm.Chars: Version
rm.Chars: s.ResFiles
