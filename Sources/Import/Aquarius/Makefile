# Top-level Makefile for tbox
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 25-Oct-94  AMcC   Created
#

DIR = tbox

COMPONENTS =\
 colourdbox\
 colourmenu\
 DCS\
 fileinfo\
 fontdbox\
 fontmenu\
 IconBar\
 menu\
 printdbox\
 proginfo\
 saveas\
 scale\
 Toolbox\
 Window\
 TinyStubs\
 Common

#
# Generic options:
#
CD      = dir
MAKE    = amu ${MFLAGS}
MKDIR   = cdir
CP      = copy
LD      = link
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

#
# Main rules:
#
#
all: ${COMPONENTS}
        @echo all: Complete

export:
        ${CP} TinyStubs.MakeROM TinyStubs.Makefile ${CPFLAGS}
        ${CP} tbox.colourdbox.MakeROM tbox.colourdbox.Makefile ${CPFLAGS}
        ${CP} tbox.colourmenu.MakeROM tbox.colourmenu.Makefile ${CPFLAGS}
        ${CP} tbox.common.MakeROM tbox.common.Makefile ${CPFLAGS}
        ${CP} tbox.dcs.MakeROM tbox.dcs.Makefile ${CPFLAGS}
        ${CP} tbox.fileinfo.MakeROM tbox.fileinfo.Makefile ${CPFLAGS}
        ${CP} tbox.fontdbox.MakeROM tbox.fontdbox.Makefile ${CPFLAGS}
        ${CP} tbox.fontmenu.MakeROM tbox.fontmenu.Makefile ${CPFLAGS}
        ${CP} tbox.iconbar.MakeROM tbox.iconbar.Makefile ${CPFLAGS}
        ${CP} tbox.menu.MakeROM tbox.menu.Makefile ${CPFLAGS}
        ${CP} tbox.printdbox.MakeROM tbox.printdbox.Makefile ${CPFLAGS}
        ${CP} tbox.proginfo.MakeROM tbox.proginfo.Makefile ${CPFLAGS}
        ${CP} tbox.saveas.MakeROM tbox.saveas.Makefile ${CPFLAGS}
        ${CP} tbox.scale.MakeROM tbox.scale.Makefile ${CPFLAGS}
        ${CP} tbox.toolbox.MakeROM tbox.toolbox.Makefile ${CPFLAGS}
        ${CP} tbox.window.MakeROM tbox.window.Makefile ${CPFLAGS}
        @echo Makefiles ready

rom: ${COMPONENTS}
        @echo rom: Complete

rom_link: ${COMPONENTS}
        @echo rom_link: Complete

clean: ${COMPONENTS}
        @echo clean: Complete

common:;      @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
colourdbox:;  @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
colourmenu:;  @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
DCS:;         @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
fileinfo:;    @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
fontdbox:;    @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
fontmenu:;    @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
IconBar:;     @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
menu:;        @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
printdbox:;   @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
proginfo:;    @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
saveas:;      @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
scale:;       @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
Toolbox:;     @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
Window:;      @echo $@ ...;  ${CD} ${DIR}.$@; ${MAKE};  back
