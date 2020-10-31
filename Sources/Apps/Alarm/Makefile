# Makefile for Alarm
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
COMPONENT  = Alarm
APP        = !${COMPONENT}
ROM_MODULE = rm.${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}

#
# Export Paths for Messages module
#
RESDIR = <resource$dir>.Resources2.${COMPONENT}
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
 ${RDIR}.!Run \
 ${RDIR}.!RunImage \
 ${RDIR}.Alarms \
 ${RDIR}.Code \
 ${LDIR}.Messages \
 ${LDIR}.Templates 

# Resources to be included in the ROM module (not in Messages module}
RESFILES =\
 ${RDIR}.code \
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
        ${CP} ${RDIR}.!Run       ${INSTDIR}.${APP}.!Run      ${CPFLAGS}
        ${CP} ${RDIR}.!RunImage  ${INSTDIR}.${APP}.!RunImage ${CPFLAGS}
        ${CP} ${RDIR}.Alarms     ${INSTDIR}.${APP}.Alarms    ${CPFLAGS}
        ${CP} ${RDIR}.Code       ${INSTDIR}.${APP}.Code      ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${INSTDIR}.${APP}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Template3D ${INSTDIR}.${APP}.Templates ${CPFLAGS}
        |
        Access ${INSTDIR}.${APP}.* lr/r
        Access ${INSTDIR}.${APP}.Alarms wr/r
        |
        @echo ${COMPONENT}: Application installed {Disc}

install_rom: ${ROM_MODULE}
        ${CP} ${ROM_MODULE} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: Module installed {ROM}

resources: ${LDIR}.!RunLink ${RDIR}.Code
        ${MKDIR} ${RESAPP}
        ${MKDIR} ${RESDIR}
        |
        ${CP} ${RDIR}.!Boot      ${RESAPP}.!Boot     ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${RESAPP}.!Help     ${CPFLAGS}
        ${CP} ${RDIR}.ROM.!Run   ${RESAPP}.!Run      ${CPFLAGS}
        |
        ${CP} ${LDIR}.!RunLink   ${RESDIR}.!RunLink  ${CPFLAGS}
        ${CP} ${RDIR}.Code       ${RESDIR}.Code      ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${RESDIR}.Messages  ${CPFLAGS}
        ${CP} ${LDIR}.Template3D ${RESDIR}.Templates ${CPFLAGS}
        |
        @echo ${COMPONENT}: resource files copied to Messages module

clean:
        ${RM} ${ROM_MODULE}
        ${RM} ${RDIR}.!RunImage
        ${RM} ${RDIR}.Code
        ${RM} s.Version
        ${WIPE} crunched.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

#
# Development rules:
# 
ResVsn:
        ${AS} ${AFLAGS} -from s.ResVsn -to rm.AlarmRes

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

${LDIR}.!RunLink: bas.!RunLink
        ${SQUISH} ${SQFLAGS} -from bas.!RunLink -to $@

# Note! name of output file (Resources.Code) is in AlarmSrc
${RDIR}.Code: bas.AlarmSrc
        /bas.AlarmSrc

#---------------------------------------------------------------------------
# Dynamic dependencies:
rm.Alarm: s.AppName
rm.Alarm: Hdr:ListOpts
rm.Alarm: Hdr:Macros
rm.Alarm: Hdr:System
rm.Alarm: Hdr:SWIs
rm.Alarm: Hdr:CPU.Generic26
rm.Alarm: Hdr:IO.GenericIO
rm.Alarm: Hdr:RISCOS
rm.Alarm: Hdr:ModHand
rm.Alarm: Hdr:Services
rm.Alarm: Hdr:Proc
rm.Alarm: Hdr:ResourceFS
rm.Alarm: s.Version
rm.Alarm: s.ResFiles
