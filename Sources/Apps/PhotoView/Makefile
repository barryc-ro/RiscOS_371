# Makefile for PhotoView
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 29-Mar-95  AMcC   Created
#

#
# Program specific options:
#
APP        = !PhotoView
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}

# Generic options:
#
MKDIR   = cdir
CC      = CRel4.Library.cc
LD      = CRel4.Library.link
SQUEEZE = CRel4.Library.squeeze
CP      = copy
RM      = remove
WIPE    = -wipe

CFLAGS  = ${THROWBACK} -c -depend !Depend -fah -Wp ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

#
# Include files
#
INCLUDES = -ICRel4.CLib,CRel4.RISC_OSLib,PCDLib

DFLAGS   = 

FILES  =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(RDIR).!RunImage\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(LDIR).Messages\
 $(RDIR).Sprites\
 $(LDIR).Templates

#
# Libraries
#
LIBS =\
 PCDLib.o.PCDlib\
 CRel4.CLib.o.stubs\
 CRel4.RISC_OSLib.o.RISC_OSLib\

OBJS =\
 o.main\
 o.pcdovervw\
 o.misc\
 o.image\
 o.sprparam\
 o.callback\
 o.palettes\
 o.scrollview\
 o.export32\
 o.winutils 

#
# Rule patterns
#
.c.o:;      ${CC} ${CFLAGS} -o $@ $<

#
# GENERIC RULES
#
all: $(FILES)
     @echo $(COMPONENT): all built

install: install_${COMPONENT}
         @echo $(COMPONENT): installed

install_PhotoView: $(FILES)
         $(MKDIR) ${INSTDIR}.${APP}; Access ${INSTDIR}.${APP} /r
         $(CP) $(RDIR).!Boot      $(INSTDIR).${APP}.!Boot       $(CPFLAGS)
         $(CP) $(LDIR).!Help      $(INSTDIR).${APP}.!Help       $(CPFLAGS)
         $(CP) $(LDIR).!Run       $(INSTDIR).${APP}.!Run        $(CPFLAGS)
         $(CP) $(RDIR).!RunImage  $(INSTDIR).${APP}.!RunImage   $(CPFLAGS)
         $(CP) $(RDIR).!Sprites   $(INSTDIR).${APP}.!Sprites    $(CPFLAGS)
         $(CP) $(RDIR).!Sprites22 $(INSTDIR).${APP}.!Sprites22  $(CPFLAGS)
         $(CP) $(LDIR).Messages   $(INSTDIR).${APP}.Messages    $(CPFLAGS)
         $(CP) $(RDIR).Sprites    $(INSTDIR).${APP}.Sprites     $(CPFLAGS)
         $(CP) $(LDIR).Templates  $(INSTDIR).${APP}.Templates   $(CPFLAGS)
         Access ${INSTDIR}.${APP}.* LR/r

install_PhotoCD: $(RDIR).PhotoCD
         $(CP) $(RDIR).PhotoCD    $(INSTDIR).PhotoCD     $(CPFLAGS)
         Access ${INSTDIR}.PhotoCD WR/r

clean:
        ${RM} ${RDIR}.!RunImage
        ${RM} abs.!RunImage
        ${WIPE} o.* ${WFLAGS}
        @echo $(COMPONENT): cleaned


# Static dependencies:
#
${RDIR}.!RunImage: abs.!RunImage
        ${SQUEEZE} -o $@ abs.!RunImage

abs.!RunImage: ${LIBS} ${OBJS}
        ${LD} -o $@ ${LIBS} ${OBJS}

#---------------------------------------------------------------------------
# Dynamic dependencies:
o.main:	c.main
o.main:	CRel4.RISC_OSLib.h.os
o.main:	CRel4.RISC_OSLib.h.wimp
o.main:	CRel4.RISC_OSLib.h.sprite
o.main:	CRel4.RISC_OSLib.h.wimpt
o.main:	CRel4.RISC_OSLib.h.win
o.main:	CRel4.RISC_OSLib.h.event
o.main:	CRel4.RISC_OSLib.h.menu
o.main:	CRel4.RISC_OSLib.h.baricon
o.main:	CRel4.RISC_OSLib.h.res
o.main:	CRel4.RISC_OSLib.h.resspr
o.main:	CRel4.RISC_OSLib.h.template
o.main:	CRel4.RISC_OSLib.h.dbox
o.main:	CRel4.RISC_OSLib.h.visdelay
o.main:	CRel4.RISC_OSLib.h.msgs
o.main:	CRel4.RISC_OSLib.h.werr
o.main:	CRel4.RISC_OSLib.h.flex
o.main:	CRel4.CLib.h.swis
o.main:	CRel4.RISC_OSLib.h.help
o.main:	CRel4.CLib.h.kernel
o.main:	CRel4.RISC_OSLib.h.sprite
o.main:	CRel4.RISC_OSLib.h.menu
o.main:	CRel4.RISC_OSLib.h.xferrecv
o.main:	h.pcdovervw
o.main:	PCDLib.h.pcdlib
o.main:	h.image
o.main:	h.misc
o.pcdovervw:	c.pcdovervw
o.pcdovervw:	CRel4.CLib.h.kernel
o.pcdovervw:	CRel4.CLib.h.swis
o.pcdovervw:	CRel4.RISC_OSLib.h.wimp
o.pcdovervw:	CRel4.RISC_OSLib.h.os
o.pcdovervw:	CRel4.RISC_OSLib.h.sprite
o.pcdovervw:	CRel4.RISC_OSLib.h.wimpt
o.pcdovervw:	CRel4.RISC_OSLib.h.win
o.pcdovervw:	CRel4.RISC_OSLib.h.msgs
o.pcdovervw:	CRel4.RISC_OSLib.h.help
o.pcdovervw:	CRel4.RISC_OSLib.h.event
o.pcdovervw:	CRel4.RISC_OSLib.h.menu
o.pcdovervw:	CRel4.RISC_OSLib.h.dbox
o.pcdovervw:	CRel4.RISC_OSLib.h.template
o.pcdovervw:	CRel4.RISC_OSLib.h.werr
o.pcdovervw:	CRel4.RISC_OSLib.h.visdelay
o.pcdovervw:	PCDLib.h.pcdlib
o.pcdovervw:	CRel4.RISC_OSLib.h.flex
o.pcdovervw:	h.pcdovervw
o.pcdovervw:	PCDLib.h.pcdlib
o.pcdovervw:	h.sprparam
o.misc:	c.misc
o.misc:	CRel4.CLib.h.kernel
o.misc:	CRel4.RISC_OSLib.h.wimp
o.misc:	CRel4.RISC_OSLib.h.os
o.misc:	CRel4.RISC_OSLib.h.sprite
o.misc:	CRel4.RISC_OSLib.h.msgs
o.misc:	CRel4.RISC_OSLib.h.help
o.misc:	CRel4.RISC_OSLib.h.event
o.misc:	CRel4.RISC_OSLib.h.menu
o.misc:	CRel4.RISC_OSLib.h.dbox
o.image:	c.image
o.image:	CRel4.CLib.h.kernel
o.image:	CRel4.CLib.h.swis
o.image:	CRel4.RISC_OSLib.h.werr
o.image:	CRel4.RISC_OSLib.h.wimpt
o.image:	CRel4.RISC_OSLib.h.wimp
o.image:	CRel4.RISC_OSLib.h.os
o.image:	CRel4.RISC_OSLib.h.sprite
o.image:	CRel4.RISC_OSLib.h.win
o.image:	CRel4.RISC_OSLib.h.help
o.image:	CRel4.RISC_OSLib.h.event
o.image:	CRel4.RISC_OSLib.h.menu
o.image:	CRel4.RISC_OSLib.h.dbox
o.image:	CRel4.RISC_OSLib.h.template
o.image:	CRel4.RISC_OSLib.h.saveas
o.image:	CRel4.RISC_OSLib.h.xfersend
o.image:	CRel4.RISC_OSLib.h.visdelay
o.image:	CRel4.RISC_OSLib.h.magnify
o.image:	CRel4.RISC_OSLib.h.txt
o.image:	CRel4.RISC_OSLib.h.akbd
o.image:	PCDLib.h.pcdlib
o.image:	CRel4.RISC_OSLib.h.msgs
o.image:	CRel4.RISC_OSLib.h.flex
o.image:	h.pcdovervw
o.image:	PCDLib.h.pcdlib
o.image:	h.sprparam
o.image:	h.callback
o.image:	h.palettes
o.image:	h.image
o.image:	h.scrollview
o.image:	h.export32
o.sprparam:	c.sprparam
o.sprparam:	CRel4.CLib.h.kernel
o.sprparam:	CRel4.CLib.h.swis
o.sprparam:	CRel4.RISC_OSLib.h.werr
o.sprparam:	CRel4.RISC_OSLib.h.wimp
o.sprparam:	CRel4.RISC_OSLib.h.os
o.sprparam:	CRel4.RISC_OSLib.h.sprite
o.sprparam:	CRel4.RISC_OSLib.h.wimpt
o.sprparam:	CRel4.RISC_OSLib.h.win
o.sprparam:	CRel4.RISC_OSLib.h.event
o.sprparam:	CRel4.RISC_OSLib.h.menu
o.sprparam:	CRel4.RISC_OSLib.h.help
o.sprparam:	CRel4.RISC_OSLib.h.dbox
o.sprparam:	CRel4.RISC_OSLib.h.template
o.sprparam:	CRel4.RISC_OSLib.h.msgs
o.sprparam:	h.pcdovervw
o.sprparam:	PCDLib.h.pcdlib
o.sprparam:	CRel4.RISC_OSLib.h.flex
o.sprparam:	h.misc
o.sprparam:	h.palettes
o.sprparam:	h.winutils
o.callback:	c.callback
o.callback:	CRel4.CLib.h.kernel
o.callback:	CRel4.CLib.h.swis
o.callback:	CRel4.RISC_OSLib.h.wimpt
o.callback:	CRel4.RISC_OSLib.h.wimp
o.callback:	CRel4.RISC_OSLib.h.os
o.callback:	CRel4.RISC_OSLib.h.sprite
o.callback:	CRel4.RISC_OSLib.h.win
o.callback:	CRel4.RISC_OSLib.h.help
o.callback:	CRel4.RISC_OSLib.h.event
o.callback:	CRel4.RISC_OSLib.h.menu
o.callback:	CRel4.RISC_OSLib.h.dbox
o.callback:	CRel4.RISC_OSLib.h.template
o.callback:	CRel4.RISC_OSLib.h.werr
o.callback:	CRel4.RISC_OSLib.h.visdelay
o.palettes:	c.palettes
o.palettes:	PCDLib.h.pcdlib
o.palettes:	CRel4.RISC_OSLib.h.msgs
o.palettes:	CRel4.RISC_OSLib.h.flex
o.palettes:	h.palettes
o.scrollview:	c.scrollview
o.scrollview:	CRel4.CLib.h.kernel
o.scrollview:	CRel4.CLib.h.swis
o.scrollview:	CRel4.RISC_OSLib.h.werr
o.scrollview:	CRel4.RISC_OSLib.h.wimpt
o.scrollview:	CRel4.RISC_OSLib.h.wimp
o.scrollview:	CRel4.RISC_OSLib.h.os
o.scrollview:	CRel4.RISC_OSLib.h.sprite
o.scrollview:	CRel4.RISC_OSLib.h.win
o.scrollview:	CRel4.RISC_OSLib.h.help
o.scrollview:	CRel4.RISC_OSLib.h.event
o.scrollview:	CRel4.RISC_OSLib.h.menu
o.scrollview:	CRel4.RISC_OSLib.h.dbox
o.scrollview:	CRel4.RISC_OSLib.h.template
o.scrollview:	CRel4.RISC_OSLib.h.visdelay
o.scrollview:	CRel4.RISC_OSLib.h.bbc
o.scrollview:	PCDLib.h.pcdlib
o.scrollview:	CRel4.RISC_OSLib.h.msgs
o.scrollview:	CRel4.RISC_OSLib.h.flex
o.scrollview:	h.pcdovervw
o.scrollview:	PCDLib.h.pcdlib
o.scrollview:	h.sprparam
o.scrollview:	h.image
o.scrollview:	h.export32
o.export32:	c.export32
o.export32:	CRel4.CLib.h.kernel
o.export32:	CRel4.CLib.h.swis
o.export32:	CRel4.RISC_OSLib.h.menu
o.export32:	CRel4.RISC_OSLib.h.saveas
o.export32:	CRel4.RISC_OSLib.h.xfersend
o.export32:	CRel4.RISC_OSLib.h.wimp
o.export32:	CRel4.RISC_OSLib.h.os
o.export32:	CRel4.RISC_OSLib.h.sprite
o.export32:	CRel4.RISC_OSLib.h.werr
o.export32:	CRel4.RISC_OSLib.h.wimpt
o.export32:	CRel4.RISC_OSLib.h.visdelay
o.export32:	PCDLib.h.pcdlib
o.export32:	CRel4.RISC_OSLib.h.msgs
o.export32:	CRel4.RISC_OSLib.h.flex
o.export32:	h.image
o.winutils:	c.winutils
o.winutils:	CRel4.RISC_OSLib.h.wimp
o.winutils:	CRel4.RISC_OSLib.h.os
o.winutils:	CRel4.RISC_OSLib.h.sprite
o.winutils:	CRel4.RISC_OSLib.h.wimpt
