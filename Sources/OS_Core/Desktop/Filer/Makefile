# Makefile for Filer
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

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
COMPONENT = Filer
SOURCE    = s.Filer
TARGET    = rm.Filer

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: rom module built

export:
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        ${CP} Resources.${LOCALE}.Templates ${RESDIR}.${COMPONENT}.Templates ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} s.TokHelpSrc
        ${AS} ${ASFLAGS} ${SOURCE}

s.TokHelpSrc: Hdr:Tokens HelpSrc
        tokenise Hdr:Tokens HelpSrc s.TokHelpSrc

# Dynamic dependencies:
rm.Filer: s.Gets
rm.Filer: Hdr:ListOpts
rm.Filer: Hdr:Macros
rm.Filer: Hdr:System
rm.Filer: Hdr:SWIs
rm.Filer: Hdr:CPU.Generic26
rm.Filer: Hdr:IO.GenericIO
rm.Filer: Hdr:RISCOS
rm.Filer: Hdr:CMOS
rm.Filer: Hdr:ModHand
rm.Filer: Hdr:FSNumbers
rm.Filer: Hdr:HighFSI
rm.Filer: Hdr:NewErrors
rm.Filer: Hdr:Wimp
rm.Filer: Hdr:WimpSpace
rm.Filer: Hdr:Messages
rm.Filer: Hdr:Sprite
rm.Filer: Hdr:UpCall
rm.Filer: Hdr:Proc
rm.Filer: Hdr:Services
rm.Filer: Hdr:VduExt
rm.Filer: Hdr:Tokens
rm.Filer: Hdr:Hourglass
rm.Filer: Hdr:Econet
rm.Filer: Hdr:Font
rm.Filer: Hdr:FileTypes
rm.Filer: Hdr:FilerAct
rm.Filer: Hdr:MsgTrans
rm.Filer: Hdr:MsgMenus
rm.Filer: Hdr:ResourceFS
rm.Filer: Hdr:Variables
rm.Filer: Hdr:DragASprit
rm.Filer: Hdr:Territory
rm.Filer: Hdr:Switcher
rm.Filer: Version
rm.Filer: s.Options
rm.Filer: s.DebugFlags
rm.Filer: s.WkspEtc
rm.Filer: s.ModHdr
rm.Filer: s.TokHelpSrc
rm.Filer: s.Commands
rm.Filer: s.Errors
rm.Filer: s.GoFiler
rm.Filer: s.ModStuff
rm.Filer: s.MiscEvents
rm.Filer: s.Open
rm.Filer: s.Close
rm.Filer: s.Redraw
rm.Filer: s.MenuIn
rm.Filer: s.MsgsIn
rm.Filer: s.DragEnd
rm.Filer: s.Clicks
rm.Filer: s.SaveDisply
rm.Filer: s.SelUtils
rm.Filer: s.FileType
rm.Filer: s.DelViews
rm.Filer: s.SendMsg
rm.Filer: s.OpenDir
rm.Filer: s.CPM
rm.Filer: s.CacheDir
rm.Filer: s.SussApplic
rm.Filer: s.SortDir
rm.Filer: s.WinUtils
rm.Filer: s.SprUtils
rm.Filer: s.StrUtils
rm.Filer: s.MiscUtils
rm.Filer: s.FreeLists
rm.Filer: s.SendAck
rm.Filer: s.PathMunge
rm.Filer: s.RMAlloc
rm.Filer: s.CMOSUtils
rm.Filer: s.MenuCreate
rm.Filer: s.IconUtils
rm.Filer: s.MenuUtils
rm.Filer: s.DecodeMenu
rm.Filer: s.SelStuff0
rm.Filer: s.OSCliInBox
rm.Filer: s.Recache
rm.Filer: s.SelStuff
rm.Filer: s.ActionStrt
rm.Filer: s.UpCall
rm.Filer: s.ResGets
