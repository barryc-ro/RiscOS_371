# Makefile for Patch
#

#
# Program specific options:
#
COMPONENT  = Patch
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
AS      = aasm
CC      = cc
CP      = copy
LD      = link
MKDIR   = cdir
RM      = remove
SQUEEZE = squeeze
SQUISH  = squish
WIPE    = -wipe

AFLAGS  = -depend !Depend -stamp -closeexec -quit -module
CFLAGS  = -c -depend !Depend -IC:
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

#
# Libraries
#
CLIB      = CLib:o.stubs
RLIB      = RISC_OSLib:o.risc_oslib

OBJS    = Main.o MsgCode.o PatchApply.o PatchParse.o Subroutins.o

FILES   =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(RDIR).BootStrap\
 Library.squeeze\
 Modules.UnSqueeze\
 $(LDIR).Messages\
 $(LDIR).ReadMe\
 Patches.PocketFS.PocketFS\
 Patches.Advance.Advance\
 $(LDIR).Templates\
 $(RDIR).Transforms


#
# Rule patterns
#
.c.o:;  ${CC} ${CFLAGS} -o $@ $<

#
# Generic rules:
#
all: $(FILES)
        @echo $(COMPONENT): all build complete

install: $(FILES)
         $(MKDIR) $(INSTDIR); Access $(INSTDIR) /r
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
         Set Alias$CPFDL CPFD %*0|MAccess $(INSTDIR).%1 LR/r
         |
         CPFDL $(RDIR) !Boot
         CPFDL $(LDIR) !Help
         CPFDL $(LDIR) !Run
         CPFDL $(RDIR) !RunImage
         CPFDL $(RDIR) !Sprites
         CPFDL $(RDIR) !Sprites22
         CPFDL $(RDIR) BootStrap
         $(MKDIR) $(INSTDIR).Library; Access $(INSTDIR).Library /r
         CPFDL @ Library.squeeze
         $(MKDIR) $(INSTDIR).Modules; Access $(INSTDIR).Modules /r
         CPFDL @ Modules.UnSqueeze
         CPFDL $(LDIR) Messages
         |
         $(MKDIR) $(INSTDIR).Patches; Access $(INSTDIR).Patches /r
         |
         $(MKDIR) $(INSTDIR).Patches.PocketFS; Access $(INSTDIR).Patches.PocketFS /r
         CPFDL @ Patches.PocketFS.PocketFS
         $(MKDIR) $(INSTDIR).Patches.Advance; Access $(INSTDIR).Patches.Advance /r
         CPFDL @ Patches.Advance.Advance
         |
         CPFDL $(LDIR) ReadMe
         CPFDL $(LDIR) Templates
         CPFDL $(RDIR) Transforms
         |
         Unset Alias$CPFDL
         Unset Alias$CPFD
         |
         @echo $(COMPONENT): installed

clean:
        ${WIPE} o.* ${WFLAGS}
        $(RM) ${RDIR}.!RunImage
        $(RM) s.TokHelpSrc
        $(RM) Modules.UnSqueeze
        @echo $(COMPONENT): cleaned

#
# Static dependencies:
#
s.TokHelpSrc: s.HelpSrc Hdr:Tokens
        Tokenise Hdr:Tokens s.HelpSrc s.TokHelpSrc

Modules.UnSqueeze: s.UnSqueeze s.TokHelpSrc
        $(AS) $(AFLAGS) -from s.UnSqueeze -to $@

$(RDIR).!RunImage: $(OBJS) $(CLIB) $(RLIB)
        $(LD) -o $@ $(OBJS) $(CLIB) $(RLIB)
        $(SQUEEZE) $@

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.Main:	c.Main
o.Main:	h.Patch
o.Main:	C:h.swis
o.Main:	C:h.kernel
o.Main:	C:h.kernel
o.Main:	C:h.os
o.Main:	C:h.wimpt
o.Main:	C:h.wimp
o.Main:	C:h.sprite
o.Main:	C:h.wimp
o.Main:	C:h.win
o.Main:	C:h.event
o.Main:	C:h.menu
o.Main:	C:h.template
o.Main:	C:h.baricon
o.Main:	C:h.menu
o.Main:	C:h.dbox
o.Main:	C:h.res
o.MsgCode:	c.MsgCode
o.MsgCode:	h.Patch
o.MsgCode:	C:h.swis
o.MsgCode:	C:h.kernel
o.MsgCode:	C:h.kernel
o.MsgCode:	C:h.os
o.MsgCode:	C:h.wimpt
o.MsgCode:	C:h.wimp
o.MsgCode:	C:h.sprite
o.MsgCode:	C:h.wimp
o.MsgCode:	C:h.win
o.MsgCode:	C:h.event
o.MsgCode:	C:h.menu
o.MsgCode:	C:h.template
o.MsgCode:	C:h.baricon
o.MsgCode:	C:h.menu
o.MsgCode:	C:h.dbox
o.MsgCode:	C:h.res
o.PatchApply:	c.PatchApply
o.PatchApply:	h.Patch
o.PatchApply:	C:h.swis
o.PatchApply:	C:h.kernel
o.PatchApply:	C:h.kernel
o.PatchApply:	C:h.os
o.PatchApply:	C:h.wimpt
o.PatchApply:	C:h.wimp
o.PatchApply:	C:h.sprite
o.PatchApply:	C:h.wimp
o.PatchApply:	C:h.win
o.PatchApply:	C:h.event
o.PatchApply:	C:h.menu
o.PatchApply:	C:h.template
o.PatchApply:	C:h.baricon
o.PatchApply:	C:h.menu
o.PatchApply:	C:h.dbox
o.PatchApply:	C:h.res
o.PatchParse:	c.PatchParse
o.PatchParse:	h.Patch
o.PatchParse:	C:h.swis
o.PatchParse:	C:h.kernel
o.PatchParse:	C:h.kernel
o.PatchParse:	C:h.os
o.PatchParse:	C:h.wimpt
o.PatchParse:	C:h.wimp
o.PatchParse:	C:h.sprite
o.PatchParse:	C:h.wimp
o.PatchParse:	C:h.win
o.PatchParse:	C:h.event
o.PatchParse:	C:h.menu
o.PatchParse:	C:h.template
o.PatchParse:	C:h.baricon
o.PatchParse:	C:h.menu
o.PatchParse:	C:h.dbox
o.PatchParse:	C:h.res
o.Subroutins:	c.Subroutins
o.Subroutins:	h.Patch
o.Subroutins:	C:h.swis
o.Subroutins:	C:h.kernel
o.Subroutins:	C:h.kernel
o.Subroutins:	C:h.os
o.Subroutins:	C:h.wimpt
o.Subroutins:	C:h.wimp
o.Subroutins:	C:h.sprite
o.Subroutins:	C:h.wimp
o.Subroutins:	C:h.win
o.Subroutins:	C:h.event
o.Subroutins:	C:h.menu
o.Subroutins:	C:h.template
o.Subroutins:	C:h.baricon
o.Subroutins:	C:h.menu
o.Subroutins:	C:h.dbox
o.Subroutins:	C:h.res
Modules.UnSqueeze: Hdr:ListOpts
Modules.UnSqueeze: Hdr:Macros
Modules.UnSqueeze: Hdr:System
Modules.UnSqueeze: Hdr:SWIs
Modules.UnSqueeze: Hdr:CPU.Generic26
Modules.UnSqueeze: Hdr:IO.GenericIO
Modules.UnSqueeze: Hdr:RISCOS
Modules.UnSqueeze: Hdr:Tokens
Modules.UnSqueeze: Hdr:Proc
Modules.UnSqueeze: Hdr:FSNumbers
Modules.UnSqueeze: Hdr:HighFSI
Modules.UnSqueeze: Hdr:FileTypes
Modules.UnSqueeze: Hdr:ModHand
Modules.UnSqueeze: Hdr:Wimp
Modules.UnSqueeze: s.TokHelpSrc
