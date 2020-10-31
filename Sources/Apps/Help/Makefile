# Makefile for Help
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
COMPONENT  = Help
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
 ${RDIR}.!Boot \
 ${LDIR}.!Help \
 ${LDIR}.!Run \
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
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.${APP}.!Boot     ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.${APP}.!Help     ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${INSTDIR}.${APP}.!Run      ${CPFLAGS}
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

resources: ${LDIR}.ROM.!RunLink
        ${MKDIR} ${RESAPP}
        ${MKDIR} ${RESDIR}
        |
        ${CP} ${LDIR}.!Help         ${RESAPP}.!Help     ${CPFLAGS}
        ${CP} ${LDIR}.ROM.!Run      ${RESAPP}.!Run      ${CPFLAGS}
        |
        ${CP} ${LDIR}.ROM.!RunLink  ${RESDIR}.!RunLink  ${CPFLAGS}
        ${CP} ${LDIR}.Messages      ${RESDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Templates     ${RESDIR}.Templates ${CPFLAGS}
        |
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${RM} ${ROM_MODULE}
        ${RM} ${RDIR}.!RunImage
        ${RM} ${LDIR}.ROM.!RunLink
        ${RM} s.Version
        ${WIPE} crunched.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

#
# Static dependencies:
#

${ROM_MODULE}: s.Main s.Version ${RESFILES}
        ${AS} ${AFLAGS} -from s.Main -to $@

s.Version: ${LDIR}.Messages
        awk -f awk.Version ${LDIR}.Messages > $@

${RDIR}.!RunImage: crunched.!RunImage
        ${SQUISH} ${SQFLAGS} -from crunched.!RunImage -to $@

crunched.!RunImage: bas.!RunImage
        crunch.!RunImage; BASIC

${LDIR}.ROM.!RunLink: bas.!RunLink
        ${SQUISH} ${SQFLAGS} -from bas.!RunLink -to $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Help: s.AppName
rm.Help: Hdr:ListOpts
rm.Help: Hdr:Macros
rm.Help: Hdr:System
rm.Help: Hdr:SWIs
rm.Help: Hdr:CPU.Generic26
rm.Help: Hdr:IO.GenericIO
rm.Help: Hdr:RISCOS
rm.Help: Hdr:ModHand
rm.Help: Hdr:Services
rm.Help: Hdr:Proc
rm.Help: Hdr:ResourceFS
rm.Help: s.Version
rm.Help: s.ResFiles
