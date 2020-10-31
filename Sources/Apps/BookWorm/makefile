# Makefile for Bookworm

# 21 Feb 97  MJS created from !Make style makefile

#
# Program specific options:
#
COMPONENT  = Bookworm
APP        = !Bookworm
MANUAL     = ${INSTDIR}.Manual
READMEDIR  = ${INSTDIR}.^
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
WORMDIR    = ${INSTDIR}.${APP}

#
# Generic options:
#
MKDIR   = cdir
AS      = objasm
CC      = cc
CMHG    = cmhg
CP      = copy
LD      = link
RM      = remove
SQUEEZE = squeeze
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

# Toolflags:
CCflags = -c -depend !Depend -IRISC_OSLib:,C:,InetInc4: -DUSE_RISCOSLIB  -DSINGLE_USER  -DCOMPAT_INET4  -DFILES_ONLY  -ff 
C++flags = -c -depend !Depend -IC: -throwback
Linkflags = -aif -c++ -o $@ 
ObjAsmflags = -throwback -NoCache -depend !Depend
CMHGflags = 
LibFileflags = -c -o $@
Squeezeflags = -o $@


all: binary.!RunImage
        @echo ${COMPONENT}: Application built (Disc)

clean:
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} binary.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

install: binary.!RunImage
        ${MKDIR} ${WORMDIR}
        ${CP} ${LDIR}.!Boot      ${WORMDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${WORMDIR}.!Help      ${CPFLAGS}
        ${CP} ${LDIR}.!Run       ${WORMDIR}.!Run       ${CPFLAGS}
        ${CP} binary.!RunImage   ${WORMDIR}.!RunImage  ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites   ${WORMDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${LDIR}.!Sprites22 ${WORMDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${LDIR}.Messages   ${WORMDIR}.Messages   ${CPFLAGS}
        ${CP} ${LDIR}.Params     ${WORMDIR}.Params     ${CPFLAGS}
        ${CP} ${LDIR}.Sprites    ${WORMDIR}.Sprites    ${CPFLAGS}
        ${CP} ${LDIR}.Templates  ${WORMDIR}.Templates  ${CPFLAGS}
        ${MKDIR} ${WORMDIR}.User
        ${CP} ${LDIR}.User.History  ${WORMDIR}.User.History  ${CPFLAGS}
        ${CP} ${LDIR}.User.HotList  ${WORMDIR}.User.HotList  ${CPFLAGS}
        Access ${WORMDIR} /r
        Access ${WORMDIR}.* lr/r
        Access ${WORMDIR}.Params wr/r
        Access ${WORMDIR}.User /r
        Access ${WORMDIR}.User.* wr/r
        @echo ${COMPONENT}: Application installed {Disc}
        ${CP} Manual.ReadMe  ${READMEDIR}.ReadMe ${CPFLAGS}
        Access ${READMEDIR}.ReadMe rw/r
        @echo ${COMPONENT}: ReadMe installed in root {Disc}
        ${MKDIR} ${MANUAL}
        ${CP} Manual.BOOK1B  ${MANUAL}.BOOK1B    ${CPFLAGS}
        ${CP} Manual.BOOK2AB ${MANUAL}.BOOK2AB   ${CPFLAGS}
        ${CP} Manual.BOOK2B  ${MANUAL}.BOOK2B    ${CPFLAGS}
        ${CP} Manual.BOOK3B  ${MANUAL}.BOOK3B    ${CPFLAGS}
        ${CP} Manual.BOOKB   ${MANUAL}.BOOKB     ${CPFLAGS}
        ${CP} Manual.INDEX   ${MANUAL}.INDEX     ${CPFLAGS}
        ${CP} Manual.AppNote ${INSTDIR}.AppNote  ${CPFLAGS}
        Access ${MANUAL} /r
        Access ${MANUAL}.BOOK1B.*  lr/r
        Access ${MANUAL}.BOOK2AB.* lr/r
        Access ${MANUAL}.BOOK2B.*  lr/r
        Access ${MANUAL}.BOOK3B.*  lr/r
        Access ${MANUAL}.BOOKB.*   lr/r
        Access ${MANUAL}.INDEX.*   lr/r
        Access ${INSTDIR}.AppNote  lr/r
        @echo ${COMPONENT}: Manual installed {Disc}


binary.!RunImage:   o.3DStuff o.Bone o.Browser o.Button o.dboxfix \
        o.DragLib o.DrawFile o.ErrorGen o.event o.Fetch o.FindProxy o.FontManage \
        o.Forms o.Graphics o.Hotlist o.IconBar o.Images o.Main o.mflex o.Panes \
        o.PlotSpr o.Printing o.Redraw o.Redraw1 o.Reformat o.Save o.saveas \
        o.Slide o.Status o.Trace o.URLv o.Utils o.win locallibs.o.flexlib HTMLLib.o.HTMLlib \
        ImageLib.o.ImageLib locallibs.o.inetlib locallibs.o.unixlib locallibs.o.RISC_OSLib C:o.stubs 
        Link $(Linkflags) o.3DStuff o.Bone o.Browser o.Button \
        o.dboxfix o.DragLib o.DrawFile o.ErrorGen o.event o.Fetch o.FindProxy \
        o.FontManage o.Forms o.Graphics o.Hotlist o.IconBar o.Images o.Main o.mflex \
        o.Panes o.PlotSpr o.Printing o.Redraw o.Redraw1 o.Reformat o.Save \
        o.saveas o.Slide o.Status o.Trace o.URLv o.Utils o.win locallibs.o.flexlib \
        HTMLLib.o.HTMLlib ImageLib.o.ImageLib locallibs.o.inetlib locallibs.o.unixlib \
        locallibs.o.RISC_OSLib C:o.stubs 



o.3DStuff:   c.3DStuff
        cc $(ccflags) -o o.3DStuff c.3DStuff 
o.Bone:   c.Bone
        cc $(ccflags) -o o.Bone c.Bone 
o.Browser:   c.Browser
        cc $(ccflags) -o o.Browser c.Browser 
o.Button:   c.Button
        cc $(ccflags) -o o.Button c.Button 
o.dboxfix:   c.dboxfix
        cc $(ccflags) -o o.dboxfix c.dboxfix 
o.DragLib:   c.DragLib
        cc $(ccflags) -o o.DragLib c.DragLib 
o.DrawFile:   c.DrawFile
        cc $(ccflags) -o o.DrawFile c.DrawFile 
o.ErrorGen:   c.ErrorGen
        cc $(ccflags) -o o.ErrorGen c.ErrorGen 
o.event:   c.event
        cc $(ccflags) -o o.event c.event 
o.Fetch:   c.Fetch
        cc $(ccflags) -o o.Fetch c.Fetch 
o.FindProxy:   c.FindProxy
        cc $(ccflags) -o o.FindProxy c.FindProxy 
o.FontManage:   c.FontManage
        cc $(ccflags) -o o.FontManage c.FontManage 
o.Forms:   c.Forms
        cc $(ccflags) -o o.Forms c.Forms 
o.Graphics:   c.Graphics
        cc $(ccflags) -o o.Graphics c.Graphics 
o.Hotlist:   c.Hotlist
        cc $(ccflags) -o o.Hotlist c.Hotlist 
o.IconBar:   c.IconBar
        cc $(ccflags) -o o.IconBar c.IconBar 
o.Images:   c.Images
        cc $(ccflags) -o o.Images c.Images 
o.Main:   c.Main
        cc $(ccflags) -o o.Main c.Main 
o.mflex:   c.mflex
        cc $(ccflags) -o o.mflex c.mflex 
o.Panes:   c.Panes
        cc $(ccflags) -o o.Panes c.Panes 
o.PlotSpr:   c.PlotSpr
        cc $(ccflags) -o o.PlotSpr c.PlotSpr 
o.Printing:   c.Printing
        cc $(ccflags) -o o.Printing c.Printing 
o.Redraw:   c.Redraw
        cc $(ccflags) -o o.Redraw c.Redraw 
o.Redraw1:   c.Redraw1
        cc $(ccflags) -o o.Redraw1 c.Redraw1 
o.Reformat:   c.Reformat
        cc $(ccflags) -o o.Reformat c.Reformat 
o.Save:   c.Save
        cc $(ccflags) -o o.Save c.Save 
o.saveas:   c.saveas
        cc $(ccflags) -o o.saveas c.saveas 
o.Slide:   c.Slide
        cc $(ccflags) -o o.Slide c.Slide 
o.Status:   c.Status
        cc $(ccflags) -o o.Status c.Status 
o.Trace:   c.Trace
        cc $(ccflags) -o o.Trace c.Trace 
o.URLv:   c.URLv
        cc $(ccflags) -o o.URLv c.URLv 
o.Utils:   c.Utils
        cc $(ccflags) -o o.Utils c.Utils 
o.win:   c.win
        cc $(ccflags) -o o.win c.win 


# Dynamic dependencies:
o.3DStuff:	c.3DStuff
o.3DStuff:	RISC_OSLib:h.os
o.3DStuff:	C:h.kernel
o.3DStuff:	RISC_OSLib:h.wimp
o.3DStuff:	RISC_OSLib:h.sprite
o.3DStuff:	RISC_OSLib:h.wimpt
o.3DStuff:	RISC_OSLib:h.win
o.3DStuff:	RISC_OSLib:h.template
o.3DStuff:	RISC_OSLib:h.menu
o.3DStuff:	RISC_OSLib:h.event
o.3DStuff:	RISC_OSLib:h.font
o.3DStuff:	RISC_OSLib:h.drawmod
o.3DStuff:	RISC_OSLib:h.bbc
o.3DStuff:	RISC_OSLib:h.coords
o.3DStuff:	RISC_OSLib:h.sprite
o.3DStuff:	RISC_OSLib:h.resspr
o.3DStuff:	RISC_OSLib:h.colourtran
o.3DStuff:	h.browser
o.3DStuff:	h.html
o.3DStuff:	RISC_OSLib:h.sprite
o.3DStuff:	h.Panes
o.3DStuff:	h.struct
o.3DStuff:	h.Fetch
o.3DStuff:	h.Defs
o.3DStuff:	h.struct
o.3DStuff:	h.Graphics
o.3DStuff:	h.Printing
o.3DStuff:	h.Overlay
o.Bone:	c.Bone
o.Bone:	RISC_OSLib:h.win
o.Bone:	RISC_OSLib:h.wimp
o.Bone:	RISC_OSLib:h.os
o.Bone:	C:h.kernel
o.Bone:	RISC_OSLib:h.sprite
o.Bone:	h.errorgen
o.Bone:	C:h.stddef
o.Bone:	C:h.stdlib
o.Bone:	RISC_OSLib:h.event
o.Bone:	RISC_OSLib:h.menu
o.Bone:	h.trace
o.Bone:	h.flex
o.Bone:	RISC_OSLib:h.os
o.Bone:	RISC_OSLib:h.wimp
o.Browser:	c.Browser
o.Browser:	C:h.stdlib
o.Browser:	C:h.stdio
o.Browser:	C:h.stddef
o.Browser:	C:h.string
o.Browser:	C:h.ctype
o.Browser:	C:h.time
o.Browser:	RISC_OSLib:h.wimp
o.Browser:	RISC_OSLib:h.os
o.Browser:	C:h.kernel
o.Browser:	RISC_OSLib:h.sprite
o.Browser:	h.flex
o.Browser:	RISC_OSLib:h.template
o.Browser:	RISC_OSLib:h.event
o.Browser:	RISC_OSLib:h.menu
o.Browser:	RISC_OSLib:h.win
o.Browser:	RISC_OSLib:h.bbc
o.Browser:	RISC_OSLib:h.wimpt
o.Browser:	h.dboxfix
o.Browser:	RISC_OSLib:h.dbox
o.Browser:	RISC_OSLib:h.help
o.Browser:	RISC_OSLib:h.msgs
o.Browser:	RISC_OSLib:h.os
o.Browser:	C:h.swis
o.Browser:	RISC_OSLib:h.print
o.Browser:	RISC_OSLib:h.coords
o.Browser:	RISC_OSLib:h.font
o.Browser:	RISC_OSLib:h.drawmod
o.Browser:	RISC_OSLib:h.sprite
o.Browser:	RISC_OSLib:h.xferrecv
o.Browser:	RISC_OSLib:h.akbd
o.Browser:	h.Button
o.Browser:	h.ErrorGen
o.Browser:	h.Browser
o.Browser:	h.html
o.Browser:	RISC_OSLib:h.sprite
o.Browser:	h.Panes
o.Browser:	h.struct
o.Browser:	h.Fetch
o.Browser:	h.Defs
o.Browser:	h.struct
o.Browser:	h.Panes
o.Browser:	h.MenuDefs
o.Browser:	h.Status
o.Browser:	h.Iconbar
o.Browser:	h.Main
o.Browser:	h.Browser
o.Browser:	h.Hotlist
o.Browser:	h.Bone
o.Browser:	h.Reformat
o.Browser:	h.Redraw1
o.Browser:	h.Defs
o.Browser:	h.FontManage
o.Browser:	h.Redraw
o.Browser:	h.Fontmanage
o.Browser:	h.struct
o.Browser:	h.Fetch
o.Browser:	h.Save
o.Browser:	RISC_OSLib:h.xfersend
o.Browser:	h.URLv
o.Browser:	h.HTMLLib
o.Browser:	h.html2_ext
o.Browser:	h.tags
o.Browser:	h.struct
o.Browser:	h.mflex
o.Browser:	h.Images
o.Browser:	h.Forms
o.Browser:	h.Printing
o.Browser:	h.Overlay
o.Browser:	h.Utils
o.Browser:	h.trace
o.Browser:	h.struct
o.Browser:	h.Fetch
o.Button:	c.Button
o.Button:	C:h.string
o.Button:	RISC_OSLib:h.akbd
o.Button:	RISC_OSLib:h.os
o.Button:	C:h.kernel
o.Button:	RISC_OSLib:h.event
o.Button:	RISC_OSLib:h.menu
o.Button:	RISC_OSLib:h.wimp
o.Button:	RISC_OSLib:h.sprite
o.Button:	RISC_OSLib:h.wimpt
o.Button:	RISC_OSLib:h.win
o.Button:	h.ErrorGen
o.Button:	h.Browser
o.Button:	C:h.stdio
o.Button:	RISC_OSLib:h.template
o.Button:	h.html
o.Button:	RISC_OSLib:h.sprite
o.Button:	h.Panes
o.Button:	h.struct
o.Button:	h.Fetch
o.Button:	h.Defs
o.Button:	h.struct
o.Button:	h.IconBar
o.Button:	h.Hotlist
o.Button:	h.flex
o.Button:	h.Defs
o.Button:	h.Fetch
o.Button:	h.Reformat
o.Button:	h.DrawFile
o.Button:	h.Button
o.dboxfix:	c.dboxfix
o.dboxfix:	h.trace
o.dboxfix:	h.flex
o.dboxfix:	RISC_OSLib:h.wimp
o.dboxfix:	RISC_OSLib:h.os
o.dboxfix:	C:h.kernel
o.dboxfix:	RISC_OSLib:h.sprite
o.dboxfix:	RISC_OSLib:h.werr
o.dboxfix:	RISC_OSLib:h.os
o.dboxfix:	RISC_OSLib:h.akbd
o.dboxfix:	RISC_OSLib:h.wimp
o.dboxfix:	RISC_OSLib:h.wimpt
o.dboxfix:	RISC_OSLib:h.win
o.dboxfix:	RISC_OSLib:h.menu
o.dboxfix:	RISC_OSLib:h.event
o.dboxfix:	RISC_OSLib:h.dbox
o.dboxfix:	RISC_OSLib:h.res
o.dboxfix:	RISC_OSLib:h.sprite
o.dboxfix:	RISC_OSLib:h.resspr
o.dboxfix:	RISC_OSLib:h.template
o.dboxfix:	RISC_OSLib:h.alarm
o.dboxfix:	RISC_OSLib:h.msgs
o.dboxfix:	RISC_OSLib:h.bbc
o.dboxfix:	RISC_OSLib:h.visdelay
o.dboxfix:	h.Slide
o.dboxfix:	h.Graphics
o.dboxfix:	RISC_OSLib:h.coords
o.dboxfix:	h.Browser
o.dboxfix:	h.html
o.dboxfix:	RISC_OSLib:h.sprite
o.dboxfix:	h.Panes
o.dboxfix:	h.struct
o.dboxfix:	h.Fetch
o.dboxfix:	h.Defs
o.dboxfix:	h.struct
o.dboxfix:	h.Printing
o.dboxfix:	h.Overlay
o.DragLib:	c.DragLib
o.DragLib:	C:h.stdlib
o.DragLib:	RISC_OSLib:h.os
o.DragLib:	C:h.kernel
o.DragLib:	RISC_OSLib:h.wimp
o.DragLib:	RISC_OSLib:h.sprite
o.DragLib:	RISC_OSLib:h.win
o.DragLib:	C:h.swis
o.DragLib:	h.Bone
o.DrawFile:	c.DrawFile
o.DrawFile:	C:h.stdlib
o.DrawFile:	C:h.stddef
o.DrawFile:	C:h.stdio
o.DrawFile:	C:h.string
o.DrawFile:	RISC_OSLib:h.wimp
o.DrawFile:	RISC_OSLib:h.os
o.DrawFile:	C:h.kernel
o.DrawFile:	RISC_OSLib:h.sprite
o.DrawFile:	RISC_OSLib:h.wimpt
o.DrawFile:	RISC_OSLib:h.sprite
o.DrawFile:	RISC_OSLib:h.drawftypes
o.DrawFile:	RISC_OSLib:h.drawfdiag
o.DrawFile:	RISC_OSLib:h.msgs
o.DrawFile:	RISC_OSLib:h.resspr
o.DrawFile:	RISC_OSLib:h.bbc
o.DrawFile:	h.Defs
o.DrawFile:	h.Main
o.DrawFile:	h.Browser
o.DrawFile:	RISC_OSLib:h.template
o.DrawFile:	h.html
o.DrawFile:	RISC_OSLib:h.sprite
o.DrawFile:	h.Panes
o.DrawFile:	h.struct
o.DrawFile:	h.Fetch
o.DrawFile:	h.struct
o.DrawFile:	h.Reformat
o.DrawFile:	h.Fontmanage
o.DrawFile:	h.Redraw
o.DrawFile:	h.Fontmanage
o.DrawFile:	h.struct
o.DrawFile:	h.Save
o.DrawFile:	RISC_OSLib:h.xfersend
o.DrawFile:	h.DrawFile
o.DrawFile:	h.Button
o.DrawFile:	h.ErrorGen
o.DrawFile:	h.Fetch
o.DrawFile:	h.Images
o.DrawFile:	h.PlotSpr
o.DrawFile:	h.Forms
o.DrawFile:	h.struct
o.DrawFile:	h.tags
o.DrawFile:	h.imagetrans
o.DrawFile:	h.flex
o.ErrorGen:	c.ErrorGen
o.ErrorGen:	C:h.stdio
o.ErrorGen:	C:h.string
o.ErrorGen:	RISC_OSLib:h.wimpt
o.ErrorGen:	RISC_OSLib:h.wimp
o.ErrorGen:	RISC_OSLib:h.os
o.ErrorGen:	C:h.kernel
o.ErrorGen:	RISC_OSLib:h.sprite
o.ErrorGen:	RISC_OSLib:h.msgs
o.ErrorGen:	h.ErrorGen
o.event:	c.event
o.event:	h.trace
o.event:	h.flex
o.event:	RISC_OSLib:h.wimp
o.event:	RISC_OSLib:h.os
o.event:	C:h.kernel
o.event:	RISC_OSLib:h.sprite
o.event:	RISC_OSLib:h.os
o.event:	RISC_OSLib:h.wimp
o.event:	RISC_OSLib:h.wimpt
o.event:	RISC_OSLib:h.win
o.event:	RISC_OSLib:h.menu
o.event:	RISC_OSLib:h.alarm
o.event:	RISC_OSLib:h.visdelay
o.event:	RISC_OSLib:h.event
o.Fetch:	c.Fetch
o.Fetch:	C:h.stdlib
o.Fetch:	C:h.stddef
o.Fetch:	C:h.string
o.Fetch:	C:h.stdio
o.Fetch:	RISC_OSLib:h.os
o.Fetch:	C:h.kernel
o.Fetch:	RISC_OSLib:h.msgs
o.Fetch:	RISC_OSLib:h.wimpt
o.Fetch:	RISC_OSLib:h.wimp
o.Fetch:	RISC_OSLib:h.sprite
o.Fetch:	RISC_OSLib:h.bbc
o.Fetch:	h.flex
o.Fetch:	RISC_OSLib:h.win
o.Fetch:	h.saveas
o.Fetch:	RISC_OSLib:h.dbox
o.Fetch:	RISC_OSLib:h.xfersend
o.Fetch:	C:h.swis
o.Fetch:	h.url
o.Fetch:	h.Browser
o.Fetch:	RISC_OSLib:h.template
o.Fetch:	h.html
o.Fetch:	RISC_OSLib:h.sprite
o.Fetch:	h.Panes
o.Fetch:	h.struct
o.Fetch:	h.Fetch
o.Fetch:	h.Defs
o.Fetch:	h.struct
o.Fetch:	h.Reformat
o.Fetch:	h.Defs
o.Fetch:	h.Status
o.Fetch:	RISC_OSLib:h.font
o.Fetch:	RISC_OSLib:h.drawmod
o.Fetch:	h.ErrorGen
o.Fetch:	h.Defs
o.Fetch:	h.IconBar
o.Fetch:	RISC_OSLib:h.menu
o.Fetch:	h.Button
o.Fetch:	h.Save
o.Fetch:	h.URLv
o.Fetch:	h.HTMLLib
o.Fetch:	h.html2_ext
o.Fetch:	h.tags
o.Fetch:	h.struct
o.Fetch:	h.mflex
o.Fetch:	h.Images
o.Fetch:	h.Forms
o.Fetch:	h.Redraw
o.Fetch:	h.Fontmanage
o.Fetch:	h.struct
o.Fetch:	h.Save
o.Fetch:	h.struct
o.FindProxy:	c.FindProxy
o.FindProxy:	C:h.swis
o.FindProxy:	C:h.kernel
o.FindProxy:	h.inetlib
o.FindProxy:	InetInc4:sys.h.types
o.FindProxy:	InetInc4:sys.h.cdefs
o.FindProxy:	InetInc4:machine.h.endian
o.FindProxy:	InetInc4:machine.h.ansi
o.FindProxy:	InetInc4:machine.h.types
o.FindProxy:	InetInc4:netinet.h.in
o.FindProxy:	h.unixlib
o.FindProxy:	h.findproxy
o.FindProxy:	InetInc4:sys.h.types
o.FindProxy:	InetInc4:netinet.h.in
o.FontManage:	c.FontManage
o.FontManage:	C:h.stdlib
o.FontManage:	C:h.stdio
o.FontManage:	C:h.string
o.FontManage:	C:h.ctype
o.FontManage:	RISC_OSLib:h.os
o.FontManage:	C:h.kernel
o.FontManage:	RISC_OSLib:h.font
o.FontManage:	RISC_OSLib:h.drawmod
o.FontManage:	RISC_OSLib:h.wimp
o.FontManage:	RISC_OSLib:h.sprite
o.FontManage:	RISC_OSLib:h.wimpt
o.FontManage:	RISC_OSLib:h.colourtran
o.FontManage:	RISC_OSLib:h.bbc
o.FontManage:	RISC_OSLib:h.menu
o.FontManage:	C:h.swis
o.FontManage:	RISC_OSLib:h.msgs
o.FontManage:	h.ErrorGen
o.FontManage:	h.FontManage
o.FontManage:	h.Utils
o.FontManage:	h.Browser
o.FontManage:	RISC_OSLib:h.template
o.FontManage:	h.html
o.FontManage:	RISC_OSLib:h.sprite
o.FontManage:	h.Panes
o.FontManage:	h.struct
o.FontManage:	h.Fetch
o.FontManage:	h.Defs
o.FontManage:	h.struct
o.FontManage:	h.Printing
o.FontManage:	h.Overlay
o.Forms:	c.Forms
o.Forms:	C:h.stdio
o.Forms:	C:h.string
o.Forms:	RISC_OSLib:h.msgs
o.Forms:	RISC_OSLib:h.wimp
o.Forms:	RISC_OSLib:h.os
o.Forms:	C:h.kernel
o.Forms:	RISC_OSLib:h.sprite
o.Forms:	RISC_OSLib:h.font
o.Forms:	RISC_OSLib:h.drawmod
o.Forms:	RISC_OSLib:h.akbd
o.Forms:	RISC_OSLib:h.coords
o.Forms:	RISC_OSLib:h.wimpt
o.Forms:	RISC_OSLib:h.bbc
o.Forms:	h.Defs
o.Forms:	h.Browser
o.Forms:	RISC_OSLib:h.template
o.Forms:	h.html
o.Forms:	RISC_OSLib:h.sprite
o.Forms:	h.Panes
o.Forms:	h.struct
o.Forms:	h.Fetch
o.Forms:	h.struct
o.Forms:	h.ErrorGen
o.Forms:	h.MFlex
o.Forms:	h.flex
o.Forms:	h.Forms
o.Forms:	h.Defs
o.Forms:	h.tags
o.Forms:	h.Redraw
o.Forms:	h.Reformat
o.Forms:	h.Fontmanage
o.Forms:	h.struct
o.Forms:	h.Reformat
o.Forms:	h.Utils
o.Forms:	h.Printing
o.Forms:	h.Overlay
o.Graphics:	c.Graphics
o.Graphics:	C:h.stddef
o.Graphics:	C:h.string
o.Graphics:	RISC_OSLib:h.resspr
o.Graphics:	RISC_OSLib:h.sprite
o.Graphics:	RISC_OSLib:h.os
o.Graphics:	C:h.kernel
o.Graphics:	RISC_OSLib:h.wimpt
o.Graphics:	RISC_OSLib:h.wimp
o.Graphics:	RISC_OSLib:h.os
o.Graphics:	RISC_OSLib:h.sprite
o.Graphics:	RISC_OSLib:h.colourtran
o.Graphics:	RISC_OSLib:h.font
o.Graphics:	RISC_OSLib:h.drawmod
o.Graphics:	RISC_OSLib:h.bbc
o.Graphics:	h.Browser
o.Graphics:	C:h.stdio
o.Graphics:	RISC_OSLib:h.template
o.Graphics:	h.html
o.Graphics:	RISC_OSLib:h.sprite
o.Graphics:	h.Panes
o.Graphics:	h.struct
o.Graphics:	h.Fetch
o.Graphics:	h.Defs
o.Graphics:	h.struct
o.Graphics:	h.Printing
o.Graphics:	h.Overlay
o.Graphics:	RISC_OSLib:h.coords
o.Hotlist:	c.Hotlist
o.Hotlist:	C:h.stdlib
o.Hotlist:	C:h.stddef
o.Hotlist:	C:h.string
o.Hotlist:	C:h.stdio
o.Hotlist:	C:h.kernel
o.Hotlist:	RISC_OSLib:h.wimp
o.Hotlist:	RISC_OSLib:h.os
o.Hotlist:	RISC_OSLib:h.sprite
o.Hotlist:	RISC_OSLib:h.coords
o.Hotlist:	h.flex
o.Hotlist:	RISC_OSLib:h.help
o.Hotlist:	RISC_OSLib:h.event
o.Hotlist:	RISC_OSLib:h.menu
o.Hotlist:	RISC_OSLib:h.dbox
o.Hotlist:	RISC_OSLib:h.wimpt
o.Hotlist:	RISC_OSLib:h.msgs
o.Hotlist:	RISC_OSLib:h.bbc
o.Hotlist:	RISC_OSLib:h.win
o.Hotlist:	h.Browser
o.Hotlist:	RISC_OSLib:h.template
o.Hotlist:	h.html
o.Hotlist:	RISC_OSLib:h.sprite
o.Hotlist:	h.Panes
o.Hotlist:	h.struct
o.Hotlist:	h.Fetch
o.Hotlist:	h.Defs
o.Hotlist:	h.struct
o.Hotlist:	h.Redraw1
o.Hotlist:	h.FontManage
o.Hotlist:	h.ErrorGen
o.Hotlist:	h.Button
o.Hotlist:	h.Save
o.Hotlist:	RISC_OSLib:h.xfersend
o.Hotlist:	h.Iconbar
o.Hotlist:	h.dboxfix
o.Hotlist:	h.Hotlist
o.Hotlist:	h.mflex
o.IconBar:	c.IconBar
o.IconBar:	C:h.stdio
o.IconBar:	C:h.stdlib
o.IconBar:	C:h.string
o.IconBar:	C:h.ctype
o.IconBar:	C:h.time
o.IconBar:	C:h.kernel
o.IconBar:	C:h.swis
o.IconBar:	RISC_OSLib:h.msgs
o.IconBar:	RISC_OSLib:h.res
o.IconBar:	RISC_OSLib:h.dbox
o.IconBar:	RISC_OSLib:h.wimp
o.IconBar:	RISC_OSLib:h.os
o.IconBar:	RISC_OSLib:h.sprite
o.IconBar:	RISC_OSLib:h.wimpt
o.IconBar:	RISC_OSLib:h.help
o.IconBar:	RISC_OSLib:h.event
o.IconBar:	RISC_OSLib:h.menu
o.IconBar:	RISC_OSLib:h.xferrecv
o.IconBar:	RISC_OSLib:h.werr
o.IconBar:	h.saveas
o.IconBar:	RISC_OSLib:h.xfersend
o.IconBar:	RISC_OSLib:h.bbc
o.IconBar:	RISC_OSLib:h.event
o.IconBar:	RISC_OSLib:h.visdelay
o.IconBar:	RISC_OSLib:h.akbd
o.IconBar:	RISC_OSLib:h.coords
o.IconBar:	RISC_OSLib:h.win
o.IconBar:	RISC_OSLib:h.menu
o.IconBar:	h.ErrorGen
o.IconBar:	h.PlotSpr
o.IconBar:	h.MenuDefs
o.IconBar:	h.Bone
o.IconBar:	h.Main
o.IconBar:	h.Browser
o.IconBar:	RISC_OSLib:h.template
o.IconBar:	h.html
o.IconBar:	RISC_OSLib:h.sprite
o.IconBar:	h.Panes
o.IconBar:	h.struct
o.IconBar:	h.Fetch
o.IconBar:	h.Defs
o.IconBar:	h.struct
o.IconBar:	h.Button
o.IconBar:	h.Hotlist
o.IconBar:	h.flex
o.IconBar:	h.FontManage
o.IconBar:	h.Redraw1
o.IconBar:	h.Defs
o.IconBar:	h.Iconbar
o.IconBar:	h.URLv
o.IconBar:	h.HTMLLib
o.IconBar:	h.html2_ext
o.IconBar:	h.tags
o.IconBar:	h.struct
o.IconBar:	h.FindProxy
o.IconBar:	InetInc4:sys.h.types
o.IconBar:	InetInc4:sys.h.cdefs
o.IconBar:	InetInc4:machine.h.endian
o.IconBar:	InetInc4:machine.h.ansi
o.IconBar:	InetInc4:machine.h.types
o.IconBar:	InetInc4:netinet.h.in
o.IconBar:	h.Forms
o.IconBar:	h.Printing
o.IconBar:	h.Overlay
o.Images:	c.Images
o.Images:	C:h.stdio
o.Images:	C:h.string
o.Images:	RISC_OSLib:h.os
o.Images:	C:h.kernel
o.Images:	RISC_OSLib:h.wimp
o.Images:	RISC_OSLib:h.sprite
o.Images:	RISC_OSLib:h.wimpt
o.Images:	RISC_OSLib:h.sprite
o.Images:	RISC_OSLib:h.bbc
o.Images:	C:h.kernel
o.Images:	RISC_OSLib:h.coords
o.Images:	RISC_OSLib:h.font
o.Images:	RISC_OSLib:h.drawmod
o.Images:	RISC_OSLib:h.msgs
o.Images:	RISC_OSLib:h.win
o.Images:	RISC_OSLib:h.resspr
o.Images:	h.Defs
o.Images:	h.Browser
o.Images:	RISC_OSLib:h.template
o.Images:	h.html
o.Images:	RISC_OSLib:h.sprite
o.Images:	h.Panes
o.Images:	h.struct
o.Images:	h.Fetch
o.Images:	h.struct
o.Images:	h.Images
o.Images:	h.ErrorGen
o.Images:	h.mflex
o.Images:	h.flex
o.Images:	h.URLv
o.Images:	h.HTMLLib
o.Images:	h.html2_ext
o.Images:	h.tags
o.Images:	h.struct
o.Images:	h.Iconbar
o.Images:	RISC_OSLib:h.menu
o.Images:	h.Reformat
o.Images:	h.Main
o.Images:	h.PlotSpr
o.Images:	h.FontManage
o.Images:	h.Redraw
o.Images:	h.Fontmanage
o.Images:	h.struct
o.Images:	h.Redraw1
o.Images:	h.Status
o.Images:	h.Save
o.Images:	RISC_OSLib:h.xfersend
o.Images:	h.Button
o.Images:	h.Status
o.Images:	h.Utils
o.Images:	h.Printing
o.Images:	h.Overlay
o.Images:	h.imagetrans
o.Main:	c.Main
o.Main:	C:h.stdlib
o.Main:	C:h.stdio
o.Main:	C:h.string
o.Main:	C:h.swis
o.Main:	C:h.kernel
o.Main:	RISC_OSLib:h.os
o.Main:	RISC_OSLib:h.bbc
o.Main:	RISC_OSLib:h.wimp
o.Main:	RISC_OSLib:h.sprite
o.Main:	RISC_OSLib:h.wimpt
o.Main:	RISC_OSLib:h.win
o.Main:	RISC_OSLib:h.sprite
o.Main:	RISC_OSLib:h.msgs
o.Main:	RISC_OSLib:h.resspr
o.Main:	h.flex
o.Main:	RISC_OSLib:h.baricon
o.Main:	RISC_OSLib:h.visdelay
o.Main:	RISC_OSLib:h.template
o.Main:	RISC_OSLib:h.event
o.Main:	RISC_OSLib:h.menu
o.Main:	RISC_OSLib:h.res
o.Main:	RISC_OSLib:h.help
o.Main:	RISC_OSLib:h.dbox
o.Main:	h.3DStuff
o.Main:	RISC_OSLib:h.coords
o.Main:	h.Graphics
o.Main:	h.DragLib
o.Main:	h.Iconbar
o.Main:	h.Bone
o.Main:	h.Iconbar
o.Main:	h.dboxfix
o.Main:	h.ErrorGen
o.Main:	h.FontManage
o.Main:	h.Browser
o.Main:	h.html
o.Main:	RISC_OSLib:h.sprite
o.Main:	h.Panes
o.Main:	h.struct
o.Main:	h.Fetch
o.Main:	h.Defs
o.Main:	h.struct
o.Main:	h.Printing
o.Main:	h.Overlay
o.Main:	h.Main
o.Main:	h.mflex
o.Main:	c.Menudefs
o.mflex:	c.mflex
o.mflex:	C:h.stdlib
o.mflex:	C:h.kernel
o.mflex:	h.flex
o.mflex:	h.Defs
o.mflex:	h.mflex
o.Panes:	c.Panes
o.Panes:	C:h.stdlib
o.Panes:	RISC_OSLib:h.wimp
o.Panes:	RISC_OSLib:h.os
o.Panes:	C:h.kernel
o.Panes:	RISC_OSLib:h.sprite
o.Panes:	RISC_OSLib:h.os
o.Panes:	RISC_OSLib:h.coords
o.PlotSpr:	c.PlotSpr
o.PlotSpr:	C:h.stdio
o.PlotSpr:	C:h.stddef
o.PlotSpr:	C:h.string
o.PlotSpr:	C:h.swis
o.PlotSpr:	C:h.kernel
o.PlotSpr:	RISC_OSLib:h.wimp
o.PlotSpr:	RISC_OSLib:h.os
o.PlotSpr:	RISC_OSLib:h.sprite
o.PlotSpr:	RISC_OSLib:h.wimpt
o.PlotSpr:	RISC_OSLib:h.os
o.PlotSpr:	RISC_OSLib:h.sprite
o.PlotSpr:	RISC_OSLib:h.colourtran
o.PlotSpr:	RISC_OSLib:h.font
o.PlotSpr:	RISC_OSLib:h.drawmod
o.PlotSpr:	RISC_OSLib:h.bbc
o.PlotSpr:	h.errorgen
o.Printing:	c.Printing
o.Printing:	C:h.signal
o.Printing:	C:h.stdlib
o.Printing:	C:h.stddef
o.Printing:	C:h.stdio
o.Printing:	C:h.string
o.Printing:	C:h.kernel
o.Printing:	C:h.swis
o.Printing:	RISC_OSLib:h.wimp
o.Printing:	RISC_OSLib:h.os
o.Printing:	RISC_OSLib:h.sprite
o.Printing:	RISC_OSLib:h.wimpt
o.Printing:	RISC_OSLib:h.os
o.Printing:	RISC_OSLib:h.win
o.Printing:	RISC_OSLib:h.dbox
o.Printing:	RISC_OSLib:h.print
o.Printing:	RISC_OSLib:h.help
o.Printing:	RISC_OSLib:h.event
o.Printing:	RISC_OSLib:h.menu
o.Printing:	RISC_OSLib:h.msgs
o.Printing:	h.flex
o.Printing:	h.PlotSpr
o.Printing:	h.Browser
o.Printing:	RISC_OSLib:h.template
o.Printing:	h.html
o.Printing:	RISC_OSLib:h.sprite
o.Printing:	h.Panes
o.Printing:	h.struct
o.Printing:	h.Fetch
o.Printing:	h.Defs
o.Printing:	h.struct
o.Printing:	h.Iconbar
o.Printing:	h.Images
o.Printing:	h.Reformat
o.Printing:	h.Redraw
o.Printing:	h.Fontmanage
o.Printing:	h.struct
o.Printing:	h.ErrorGen
o.Printing:	h.Main
o.Printing:	h.Fetch
o.Printing:	h.Button
o.Printing:	h.Utils
o.Printing:	h.Defs
o.Printing:	h.Printing
o.Printing:	h.Overlay
o.Redraw:	c.Redraw
o.Redraw:	C:h.stdlib
o.Redraw:	C:h.stddef
o.Redraw:	C:h.stdio
o.Redraw:	C:h.string
o.Redraw:	RISC_OSLib:h.wimp
o.Redraw:	RISC_OSLib:h.os
o.Redraw:	C:h.kernel
o.Redraw:	RISC_OSLib:h.sprite
o.Redraw:	RISC_OSLib:h.bbc
o.Redraw:	RISC_OSLib:h.colourtran
o.Redraw:	RISC_OSLib:h.font
o.Redraw:	RISC_OSLib:h.drawmod
o.Redraw:	RISC_OSLib:h.os
o.Redraw:	RISC_OSLib:h.font
o.Redraw:	RISC_OSLib:h.coords
o.Redraw:	RISC_OSLib:h.sprite
o.Redraw:	RISC_OSLib:h.resspr
o.Redraw:	RISC_OSLib:h.msgs
o.Redraw:	RISC_OSLib:h.wimpt
o.Redraw:	RISC_OSLib:h.win
o.Redraw:	h.Browser
o.Redraw:	RISC_OSLib:h.template
o.Redraw:	h.html
o.Redraw:	RISC_OSLib:h.sprite
o.Redraw:	h.Panes
o.Redraw:	h.struct
o.Redraw:	h.Fetch
o.Redraw:	h.Defs
o.Redraw:	h.struct
o.Redraw:	h.Reformat
o.Redraw:	h.Fontmanage
o.Redraw:	h.Redraw1
o.Redraw:	h.ErrorGen
o.Redraw:	h.Images
o.Redraw:	h.Iconbar
o.Redraw:	RISC_OSLib:h.menu
o.Redraw:	h.Redraw
o.Redraw:	h.Fontmanage
o.Redraw:	h.struct
o.Redraw:	h.PlotSpr
o.Redraw:	h.Main
o.Redraw:	h.Fetch
o.Redraw:	h.Forms
o.Redraw:	h.Printing
o.Redraw:	h.Overlay
o.Redraw:	h.Utils
o.Redraw:	h.struct
o.Redraw:	h.tags
o.Redraw1:	c.Redraw1
o.Redraw1:	RISC_OSLib:h.wimp
o.Redraw1:	RISC_OSLib:h.os
o.Redraw1:	C:h.kernel
o.Redraw1:	RISC_OSLib:h.sprite
o.Redraw1:	RISC_OSLib:h.coords
o.Redraw1:	RISC_OSLib:h.bbc
o.Redraw1:	h.3DStuff
o.Reformat:	c.Reformat
o.Reformat:	C:h.stdlib
o.Reformat:	C:h.stddef
o.Reformat:	C:h.string
o.Reformat:	RISC_OSLib:h.os
o.Reformat:	C:h.kernel
o.Reformat:	RISC_OSLib:h.font
o.Reformat:	RISC_OSLib:h.drawmod
o.Reformat:	RISC_OSLib:h.wimp
o.Reformat:	RISC_OSLib:h.sprite
o.Reformat:	RISC_OSLib:h.wimpt
o.Reformat:	RISC_OSLib:h.wimp
o.Reformat:	RISC_OSLib:h.win
o.Reformat:	RISC_OSLib:h.sprite
o.Reformat:	RISC_OSLib:h.bbc
o.Reformat:	RISC_OSLib:h.resspr
o.Reformat:	RISC_OSLib:h.msgs
o.Reformat:	h.Main
o.Reformat:	h.Browser
o.Reformat:	C:h.stdio
o.Reformat:	RISC_OSLib:h.template
o.Reformat:	h.html
o.Reformat:	RISC_OSLib:h.sprite
o.Reformat:	h.Panes
o.Reformat:	h.struct
o.Reformat:	h.Fetch
o.Reformat:	h.Defs
o.Reformat:	h.struct
o.Reformat:	h.FontManage
o.Reformat:	h.Redraw
o.Reformat:	h.Reformat
o.Reformat:	h.Fontmanage
o.Reformat:	h.struct
o.Reformat:	h.ErrorGen
o.Reformat:	h.Button
o.Reformat:	h.Reformat
o.Reformat:	h.Panes
o.Reformat:	h.Images
o.Reformat:	h.Fetch
o.Reformat:	h.Forms
o.Reformat:	h.Iconbar
o.Reformat:	RISC_OSLib:h.menu
o.Reformat:	h.Utils
o.Reformat:	h.Printing
o.Reformat:	h.Overlay
o.Reformat:	h.struct
o.Reformat:	h.tags
o.Reformat:	C:h.stdio
o.Save:	c.Save
o.Save:	C:h.stdlib
o.Save:	C:h.stddef
o.Save:	C:h.stdio
o.Save:	C:h.string
o.Save:	C:h.kernel
o.Save:	RISC_OSLib:h.xfersend
o.Save:	RISC_OSLib:h.wimp
o.Save:	RISC_OSLib:h.os
o.Save:	RISC_OSLib:h.sprite
o.Save:	h.saveas
o.Save:	RISC_OSLib:h.dbox
o.Save:	RISC_OSLib:h.os
o.Save:	RISC_OSLib:h.wimpt
o.Save:	h.ErrorGen
o.Save:	h.Defs
o.Save:	h.Save
o.saveas:	c.saveas
o.saveas:	RISC_OSLib:h.os
o.saveas:	C:h.kernel
o.saveas:	RISC_OSLib:h.bbc
o.saveas:	RISC_OSLib:h.wimp
o.saveas:	RISC_OSLib:h.sprite
o.saveas:	RISC_OSLib:h.wimpt
o.saveas:	RISC_OSLib:h.win
o.saveas:	RISC_OSLib:h.dbox
o.saveas:	RISC_OSLib:h.xfersend
o.saveas:	RISC_OSLib:h.fileicon
o.saveas:	RISC_OSLib:h.werr
o.saveas:	RISC_OSLib:h.menu
o.saveas:	RISC_OSLib:h.event
o.saveas:	RISC_OSLib:h.msgs
o.saveas:	RISC_OSLib:h.help
o.Slide:	c.Slide
o.Slide:	C:h.stdio
o.Slide:	C:h.string
o.Slide:	C:h.stdlib
o.Slide:	RISC_OSLib:h.wimp
o.Slide:	RISC_OSLib:h.os
o.Slide:	C:h.kernel
o.Slide:	RISC_OSLib:h.sprite
o.Slide:	RISC_OSLib:h.win
o.Slide:	RISC_OSLib:h.wimpt
o.Slide:	RISC_OSLib:h.coords
o.Slide:	h.Bone
o.Slide:	h.3dstuff
o.Slide:	h.Graphics
o.Status:	c.Status
o.Status:	C:h.stddef
o.Status:	C:h.stdarg
o.Status:	C:h.stdio
o.Status:	C:h.string
o.Status:	RISC_OSLib:h.wimp
o.Status:	RISC_OSLib:h.os
o.Status:	C:h.kernel
o.Status:	RISC_OSLib:h.sprite
o.Status:	RISC_OSLib:h.wimpt
o.Status:	RISC_OSLib:h.event
o.Status:	RISC_OSLib:h.menu
o.Status:	RISC_OSLib:h.bbc
o.Status:	RISC_OSLib:h.coords
o.Status:	RISC_OSLib:h.msgs
o.Status:	RISC_OSLib:h.font
o.Status:	RISC_OSLib:h.drawmod
o.Status:	RISC_OSLib:h.colourtran
o.Status:	RISC_OSLib:h.sprite
o.Status:	RISC_OSLib:h.resspr
o.Status:	C:h.swis
o.Status:	RISC_OSLib:h.win
o.Status:	h.Browser
o.Status:	RISC_OSLib:h.template
o.Status:	h.html
o.Status:	RISC_OSLib:h.sprite
o.Status:	h.Panes
o.Status:	h.struct
o.Status:	h.Fetch
o.Status:	h.Defs
o.Status:	h.struct
o.Status:	h.Redraw1
o.Status:	h.IconBar
o.Status:	h.ErrorGen
o.Status:	h.PlotSpr
o.Status:	h.Main
o.Status:	h.Button
o.Status:	h.FontManage
o.Status:	h.Status
o.Status:	h.Images
o.Status:	h.mflex
o.Status:	h.flex
o.Trace:	c.Trace
o.Trace:	RISC_OSLib:h.bbc
o.Trace:	RISC_OSLib:h.os
o.Trace:	C:h.kernel
o.Trace:	C:h.string
o.Trace:	h.flex
o.Trace:	RISC_OSLib:h.wimp
o.Trace:	RISC_OSLib:h.sprite
o.Trace:	h.mflex
o.Trace:	h.Defs
o.URLv:	c.URLv
o.URLv:	C:h.string
o.URLv:	C:h.kernel
o.URLv:	RISC_OSLib:h.win
o.URLv:	RISC_OSLib:h.wimp
o.URLv:	RISC_OSLib:h.os
o.URLv:	RISC_OSLib:h.sprite
o.URLv:	h.errorgen
o.URLv:	h.URLv
o.URLv:	h.HTMLLib
o.URLv:	h.html2_ext
o.URLv:	h.tags
o.URLv:	h.struct
o.URLv:	C:h.string
o.URLv:	C:h.stdio
o.URLv:	RISC_OSLib:h.os
o.URLv:	h.flex
o.URLv:	RISC_OSLib:h.dbox
o.URLv:	RISC_OSLib:h.msgs
o.URLv:	RISC_OSLib:h.help
o.URLv:	RISC_OSLib:h.event
o.URLv:	RISC_OSLib:h.menu
o.URLv:	h.mflex
o.URLv:	h.Defs
o.URLv:	h.HTMLLib
o.URLv:	h.Browser
o.URLv:	RISC_OSLib:h.template
o.URLv:	h.html
o.URLv:	RISC_OSLib:h.sprite
o.URLv:	h.Panes
o.URLv:	h.struct
o.URLv:	h.Fetch
o.URLv:	h.struct
o.URLv:	h.ErrorGen
o.Utils:	c.Utils
o.Utils:	C:h.stdlib
o.Utils:	C:h.stdio
o.Utils:	C:h.string
o.Utils:	C:h.stdarg
o.Utils:	C:h.swis
o.Utils:	C:h.kernel
o.Utils:	C:h.kernel
o.Utils:	RISC_OSLib:h.wimp
o.Utils:	RISC_OSLib:h.os
o.Utils:	RISC_OSLib:h.sprite
o.Utils:	RISC_OSLib:h.wimpt
o.Utils:	RISC_OSLib:h.os
o.Utils:	RISC_OSLib:h.win
o.Utils:	RISC_OSLib:h.dbox
o.Utils:	RISC_OSLib:h.print
o.Utils:	RISC_OSLib:h.help
o.Utils:	RISC_OSLib:h.event
o.Utils:	RISC_OSLib:h.menu
o.Utils:	RISC_OSLib:h.msgs
o.Utils:	h.Browser
o.Utils:	RISC_OSLib:h.template
o.Utils:	h.html
o.Utils:	RISC_OSLib:h.sprite
o.Utils:	h.Panes
o.Utils:	h.struct
o.Utils:	h.Fetch
o.Utils:	h.Defs
o.Utils:	h.struct
o.Utils:	h.Printing
o.Utils:	h.Overlay
o.Utils:	h.Utils
o.win:	c.win
o.win:	h.trace
o.win:	h.flex
o.win:	RISC_OSLib:h.wimp
o.win:	RISC_OSLib:h.os
o.win:	C:h.kernel
o.win:	RISC_OSLib:h.sprite
o.win:	RISC_OSLib:h.os
o.win:	RISC_OSLib:h.wimp
o.win:	RISC_OSLib:h.werr
o.win:	RISC_OSLib:h.wimpt
o.win:	RISC_OSLib:h.event
o.win:	RISC_OSLib:h.menu
o.win:	RISC_OSLib:h.msgs
o.win:	RISC_OSLib:h.visdelay
o.win:	RISC_OSLib:h.win
