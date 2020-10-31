# Makefile for Colour Translation module
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
# 10-Mar-95  GPS          Changed method for building ROM tables.
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
CC      = cc
RM      = remove
CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module -To $@ -From
CPFLAGS = ~cfr~v
CLIB    = CLIB:o.stubs
#
# Program specific options:
#
COMPONENT = Colours
SOURCE    = MakeNew
TARGET    = rm.Colours
EXPORTS   = ${EXP_HDR}.ColourTran

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

resources: Palettes.8desktop
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages ${CPFLAGS}
        ${CP} Palettes ${RESDIR}.${COMPONENT}.Palettes ${CPFLAGS}
        ${CP} Tables   ${RESDIR}.${COMPONENT}.Tables   ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE}
        ${AS} ${ASFLAGS} ${SOURCE}

${EXP_HDR}.ColourTran: hdr.ColourTran
        ${CP} hdr.ColourTran $@ ${CPFLAGS}

Colours200: MakeOld
        ${AS} ${ASFLAGS} MakeOld
        @echo ${COMPONENT}: Colours200 built

MkTables.o.maketables: MkTables.c.maketables
        ${CC} $(ccflags) -o $@ MkTables.c.maketables

MkTables.maketables:   MkTables.o.maketables ${CLIB} 
        link $(linkflags) -o $@ MkTables.o.maketables ${CLIB}

Palettes.8desktop: MkTables.maketables rm.Colours
        rmload rm.Colours
        MkTables.maketables @  
        settype Tables.8greys text
        settype Tables.4greys text
        MkTables.dosqueeze
        
# Dynamic dependencies:
MkTables.o.maketables:	MkTables.c.maketables
MkTables.o.maketables:	C:h.swis
MkTables.o.maketables:	C:h.kernel
rm.Colours: s.Header
rm.Colours: hdr:ListOpts
rm.Colours: hdr:Macros
rm.Colours: hdr:System
rm.Colours: Hdr:SWIs
rm.Colours: Hdr:CPU.Generic26
rm.Colours: Hdr:IO.GenericIO
rm.Colours: Hdr:RISCOS
rm.Colours: hdr:FSNumbers
rm.Colours: hdr:ModHand
rm.Colours: hdr:NewErrors
rm.Colours: hdr:VduExt
rm.Colours: hdr:Services
rm.Colours: hdr:Font
rm.Colours: hdr:Sprite
rm.Colours: hdr:PublicWS
rm.Colours: hdr:ExtraLong
rm.Colours: hdr:Proc
rm.Colours: hdr:MsgTrans
rm.Colours: hdr:DDVMacros
rm.Colours: hdr:PaletteV
rm.Colours: hdr:ColourTran
rm.Colours: hdr:Symbols
rm.Colours: hdr:HostFS
rm.Colours: hdr:variables
rm.Colours: hdr:NDRDebug
rm.Colours: Version
rm.Colours: s.Commons
rm.Colours: s.MainSWIs
rm.Colours: s.Cache
rm.Colours: s.FontColour
rm.Colours: s.Dither
rm.Colours: s.NewModels
rm.Colours: s.Palettes
rm.Colours: s.MsgCode
rm.Colours: s.FileCal
rm.Colours: s.Calibrate
rm.Colours: s.DevicePal
rm.Colours: s.DevicePal2
rm.Colours: s.Enhanced
rm.Colours: s.Tables32K
