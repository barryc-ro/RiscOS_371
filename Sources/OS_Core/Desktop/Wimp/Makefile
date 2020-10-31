# Makefile for Wimp
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name    Description
# ----       ----    -----------
# 25-May-94  AMcC    Created.
# 18-Oct-94  AMcC    Template3D now copied to Resources as 'Templates'
#                    Now correctly copies Tools3D to Resources:...Tools
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR   = cdir
AS      = aasm
CP      = copy
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = Wimp
SOURCE    = s.Wimp
TARGET    = rm.Wimp
EXPORTS   = ${EXP_HDR}.Wimp \
            ${EXP_HDR}.WimpSpace

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages   ${RESDIR}.${COMPONENT}.Messages   ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Template3D ${RESDIR}.${COMPONENT}.Templates  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Sprites    ${RESDIR}.${COMPONENT}.Sprites    ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Sprites22  ${RESDIR}.${COMPONENT}.Sprites22  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Tools3d    ${RESDIR}.${COMPONENT}.Tools      ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.Wimp: hdr.Wimp
        ${CP} hdr.Wimp $@ ${CPFLAGS}

${EXP_HDR}.WimpSpace: hdr.WimpSpace
        ${CP} hdr.WimpSpace $@ ${CPFLAGS}

# Dynamic dependencies:
rm.Wimp: Hdr:ListOpts
rm.Wimp: Hdr:Macros
rm.Wimp: Hdr:System
rm.Wimp: Hdr:SWIs
rm.Wimp: Hdr:CPU.Generic26
rm.Wimp: Hdr:IO.GenericIO
rm.Wimp: Hdr:RISCOS
rm.Wimp: Hdr:CMOS
rm.Wimp: Hdr:PublicWS
rm.Wimp: Hdr:ModHand
rm.Wimp: Hdr:Proc
rm.Wimp: Hdr:EnvNumbers
rm.Wimp: Hdr:Services
rm.Wimp: Hdr:UpCall
rm.Wimp: Hdr:VduExt
rm.Wimp: Hdr:FSNumbers
rm.Wimp: Hdr:HighFSI
rm.Wimp: Hdr:HostFS
rm.Wimp: Hdr:NDRDebug
rm.Wimp: Hdr:Font
rm.Wimp: Hdr:Wimp
rm.Wimp: Hdr:Messages
rm.Wimp: Hdr:NewErrors
rm.Wimp: Hdr:Sprite
rm.Wimp: Hdr:Variables
rm.Wimp: Hdr:Hourglass
rm.Wimp: Hdr:ResourceFS
rm.Wimp: Hdr:Portable
rm.Wimp: Hdr:MsgTrans
rm.Wimp: hdr:ColourTran
rm.Wimp: hdr:FPEmulator
rm.Wimp: hdr:Territory
rm.Wimp: hdr:Switcher
rm.Wimp: hdr:PDriver
rm.Wimp: Version
rm.Wimp: hdr.WIMPMacros
rm.Wimp: s.Options
rm.Wimp: s.Wimp01
rm.Wimp: s.!Palette
rm.Wimp: s.Memory
rm.Wimp: s.Wimp02
rm.Wimp: s.Watchdog
rm.Wimp: s.Tiling
rm.Wimp: s.Wimp03
rm.Wimp: s.Wimp04
rm.Wimp: s.Wimp05
rm.Wimp: s.Wimp06
rm.Wimp: s.Iconbar
rm.Wimp: s.Wimp07
rm.Wimp: s.ProgErrs
rm.Wimp: s.W08_oldway
rm.Wimp: s.Wimp08
rm.Wimp: s.Wimp09
rm.Wimp: s.Wimp10
rm.Wimp: s.NewSWIs
