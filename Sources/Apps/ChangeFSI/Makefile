# Makefile for ChangeFSI
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 30-Sep-94  AMcC   Made suitable for Black build (incorporates JPEG directory)
# 29-Oct-94  AMcC   Use crunch.ChangeFSI to do the crunching (bascrunch was unreliable)
# 02-Nov-94  MS     Add JPEGprint
# 18-Jan-95  GPS    Changed to use IJG release 5 software.
# 01-Mar-95  GPS    Changed to include new documentation.
#

#
# Program specific options:
#
COMPONENT  = ChangeFSI
APP        = !ChangeFSI
DDIR       = DataFiles
LDIR       = ${LOCALE}
SDIR       = source
INSTDIR    = ${INSTDIR}.${APP}

VPATH      = @ JPEG

#
# Tools:
#
MKDIR     = cdir
CC        = cc
CP        = copy
LD        = link
RM        = remove
SQUEEZE   = squeeze -f
WIPE      = -wipe

#
# Tool flags:
#
DFLAGS  = -DDEFAULT_MAX_MEM=655360 -DHAVE_BOOLEAN
CFLAGS  = -IC: -c -depend !Depend ${INCLUDES} ${DFLAGS}
CPFLAGS = ~cfr~v
CRFLAGS = %11101
WFLAGS  = ~c~v

INCLUDES = 

#
# Libraries
#
CLIB   = CLIB:o.stubs

FILES  =\
 $(LDIR).!Help\
 $(LDIR).!Run\
 $(DDIR).!Boot\
 $(LDIR).!Sprites\
 $(LDIR).!Sprites22\
 $(DDIR).Documents.256sprites\
 $(DDIR).Documents.CmdBasUse\
 $(DDIR).Documents.DesktopUse\
 $(DDIR).Documents.Formats\
 $(DDIR).Documents.JPEGInfo\
 $(DDIR).Documents.Theory\
 $(DDIR).hpcdtoppm\
 $(LDIR).3DTemplate\
 $(LDIR).Templates\
 $(LDIR).Messages\
 $(DDIR).djpeg.djpeg\
 $(DDIR).djpeg.!Run\
 $(DDIR).djpeg.HourOn\
 $(DDIR).djpeg.HourOff\
 $(DDIR).ChangeFSI\
 $(DDIR).cjpeg \
 ${DDIR}.JPEGprint.!Run \
 ${DDIR}.JPEGprint.JPEGprint

#
# JPEG object files
#

# object files common to cjpeg and djpeg
COMOBJS =\
 jutils.o\
 jerror.o\
 jmemmgr.o\
 jmemnobs.o\
 jcomapi.o

# compression objects
CLIBOBJS =\
 jcapi.o\
 jcparam.o\
 jdatadst.o\
 jcmaster.o\
 jcmarker.o\
 jcmainct.o\
 jcprepct.o\
 jccoefct.o\
 jccolor.o\
 jcsample.o\
 jchuff.o\
 jcdctmgr.o\
 jfdctfst.o\
 jfdctflt.o\
 jfdctint.o\
 cjpeg.o\
 rdppm.o\
 rdgif.o\
 rdtarga.o\
 rdrle.o\
 rdbmp.o

# decompression objects
DLIBOBJS =\
 jdapi.o\
 jdatasrc.o\
 jdmaster.o\
 jdmarker.o\
 jdmainct.o\
 jdcoefct.o \
 jdpostct.o\
 jddctmgr.o\
 jidctfst.o\
 jidctflt.o\
 jidctint.o\
 jidctred.o \
 jdhuff.o\
 jdsample.o\
 jdcolor.o\
 jquant1.o\
 jquant2.o\
 jdmerge.o\
 djpeg.o\
 wrgif.o\
 wrppm.o\
 wrrle.o\
 wrtarga.o\
 wrbmp.o\
 rdcolmap.o

COBJS = ${CLIBOBJS} ${COMOBJS}
DOBJS = ${DLIBOBJS} ${COMOBJS}


#
# Rule patterns:
#
.c.o:;  ${CC} ${CFLAGS} -o $@ $<

#
# GENERIC RULES
#                  
all: $(FILES)
          @echo $(COMPONENT): all built

install: $(FILES)
         Set Alias$CPFD $(CP) %0.%1 $(INSTDIR).%1 $(CPFLAGS)
         Set Alias$CPFDL CPFD %*0|MAccess $(INSTDIR).%1 LR/r
         |
         ${MKDIR} ${INSTDIR}
         Access ${INSTDIR} /r
         |
         CPFDL $(LDIR) !Help
         CPFDL $(LDIR) !Run
         CPFDL $(DDIR) !Boot
         CPFDL $(LDIR) !Sprites
         CPFDL $(LDIR) !Sprites22
         $(MKDIR) $(INSTDIR).Documents
         CPFDL $(DDIR) Documents.256sprites
         CPFDL $(DDIR) Documents.CmdBasUse
         CPFDL $(DDIR) Documents.DesktopUse
         CPFDL $(DDIR) Documents.Formats
         CPFDL $(DDIR) Documents.JPEGInfo
         CPFDL $(DDIR) Documents.Theory
         CPFDL $(DDIR) hpcdtoppm
         CPFDL $(LDIR) Messages
         CPFDL $(LDIR) Templates
         CPFDL $(LDIR) 3dTemplate
         CPFDL $(DDIR) cjpeg
         $(MKDIR) $(INSTDIR).djpeg
         CPFDL $(DDIR) djpeg.djpeg
         CPFDL $(DDIR) djpeg.!Run
         CPFDL $(DDIR) djpeg.HourOn
         CPFDL $(DDIR) djpeg.HourOff
         CPFDL $(DDIR) ChangeFSI
         $(MKDIR) $(INSTDIR).JPEGprint
         CPFDL $(DDIR) JPEGprint.!Run
         CPFDL $(DDIR) JPEGprint.JPEGprint
         |
         Unset Alias$CPFDL
         Unset Alias$CPFD
         |
         @echo $(COMPONENT): installed

clean:
         $(RM) $(DDIR).ChangeFSI
         $(RM) $(DDIR).DJpeg.DJpeg
         $(RM) $(DDIR).CJpeg
         $(RM) $(DDIR).JPEGprint.JPEGprint
         $(RM) CJpeg
         $(RM) DJpeg
         ${WIPE} o.* ${WFLAGS}
         @echo $(COMPONENT): cleaned

#------------------------------------------------------------------------------
# ChangeFSI
#------------------------------------------------------------------------------
$(DDIR).ChangeFSI: ${SDIR}.ChangeFSI
        crunch.ChangeFSI; BASIC


#------------------------------------------------------------------------------
# JPEGprint
#------------------------------------------------------------------------------
$(DDIR).JPEGprint.JPEGprint: o.JPEGprint ${CLIB}
        ${LD} -o $@ o.JPEGprint ${CLIB}
        ${SQUEEZE} $@


#------------------------------------------------------------------------------
# JPEG
#------------------------------------------------------------------------------
$(DDIR).CJpeg: ${COBJS} ${CLIB}
        ${LD} -o $@ ${COBJS} ${CLIB}
        ${SQUEEZE} $@

$(DDIR).DJpeg.DJpeg: ${DOBJS} ${CLIB}
        ${LD} -o $@ ${DOBJS} ${CLIB}
        ${SQUEEZE} $@

# Dynamic dependencies:
o.jdapi:	JPEG.c.jdapi
o.jdapi:	JPEG.h.jinclude
o.jdapi:	JPEG.h.jconfig
o.jdapi:	JPEG.h.jpeglib
o.jdapi:	JPEG.h.jmorecfg
o.jdapi:	JPEG.h.jpegint
o.jdapi:	JPEG.h.jerror
o.jdatasrc:	JPEG.c.jdatasrc
o.jdatasrc:	JPEG.h.jinclude
o.jdatasrc:	JPEG.h.jconfig
o.jdatasrc:	JPEG.h.jpeglib
o.jdatasrc:	JPEG.h.jmorecfg
o.jdatasrc:	JPEG.h.jerror
o.jdmaster:	JPEG.c.jdmaster
o.jdmaster:	JPEG.h.jinclude
o.jdmaster:	JPEG.h.jconfig
o.jdmaster:	JPEG.h.jpeglib
o.jdmaster:	JPEG.h.jmorecfg
o.jdmaster:	JPEG.h.jpegint
o.jdmaster:	JPEG.h.jerror
o.jdmarker:	JPEG.c.jdmarker
o.jdmarker:	JPEG.h.jinclude
o.jdmarker:	JPEG.h.jconfig
o.jdmarker:	JPEG.h.jpeglib
o.jdmarker:	JPEG.h.jmorecfg
o.jdmarker:	JPEG.h.jpegint
o.jdmarker:	JPEG.h.jerror
o.jdmainct:	JPEG.c.jdmainct
o.jdmainct:	JPEG.h.jinclude
o.jdmainct:	JPEG.h.jconfig
o.jdmainct:	JPEG.h.jpeglib
o.jdmainct:	JPEG.h.jmorecfg
o.jdmainct:	JPEG.h.jpegint
o.jdmainct:	JPEG.h.jerror
o.jdcoefct:	JPEG.c.jdcoefct
o.jdcoefct:	JPEG.h.jinclude
o.jdcoefct:	JPEG.h.jconfig
o.jdcoefct:	JPEG.h.jpeglib
o.jdcoefct:	JPEG.h.jmorecfg
o.jdcoefct:	JPEG.h.jpegint
o.jdcoefct:	JPEG.h.jerror
o.jdpostct:	JPEG.c.jdpostct
o.jdpostct:	JPEG.h.jinclude
o.jdpostct:	JPEG.h.jconfig
o.jdpostct:	JPEG.h.jpeglib
o.jdpostct:	JPEG.h.jmorecfg
o.jdpostct:	JPEG.h.jpegint
o.jdpostct:	JPEG.h.jerror
o.jddctmgr:	JPEG.c.jddctmgr
o.jddctmgr:	JPEG.h.jinclude
o.jddctmgr:	JPEG.h.jconfig
o.jddctmgr:	JPEG.h.jpeglib
o.jddctmgr:	JPEG.h.jmorecfg
o.jddctmgr:	JPEG.h.jpegint
o.jddctmgr:	JPEG.h.jerror
o.jddctmgr:	JPEG.h.jdct
o.jidctfst:	JPEG.c.jidctfst
o.jidctfst:	JPEG.h.jinclude
o.jidctfst:	JPEG.h.jconfig
o.jidctfst:	JPEG.h.jpeglib
o.jidctfst:	JPEG.h.jmorecfg
o.jidctfst:	JPEG.h.jpegint
o.jidctfst:	JPEG.h.jerror
o.jidctfst:	JPEG.h.jdct
o.jidctflt:	JPEG.c.jidctflt
o.jidctflt:	JPEG.h.jinclude
o.jidctflt:	JPEG.h.jconfig
o.jidctflt:	JPEG.h.jpeglib
o.jidctflt:	JPEG.h.jmorecfg
o.jidctflt:	JPEG.h.jpegint
o.jidctflt:	JPEG.h.jerror
o.jidctflt:	JPEG.h.jdct
o.jidctint:	JPEG.c.jidctint
o.jidctint:	JPEG.h.jinclude
o.jidctint:	JPEG.h.jconfig
o.jidctint:	JPEG.h.jpeglib
o.jidctint:	JPEG.h.jmorecfg
o.jidctint:	JPEG.h.jpegint
o.jidctint:	JPEG.h.jerror
o.jidctint:	JPEG.h.jdct
o.jidctred:	JPEG.c.jidctred
o.jidctred:	JPEG.h.jinclude
o.jidctred:	JPEG.h.jconfig
o.jidctred:	JPEG.h.jpeglib
o.jidctred:	JPEG.h.jmorecfg
o.jidctred:	JPEG.h.jpegint
o.jidctred:	JPEG.h.jerror
o.jidctred:	JPEG.h.jdct
o.jdhuff:	JPEG.c.jdhuff
o.jdhuff:	JPEG.h.jinclude
o.jdhuff:	JPEG.h.jconfig
o.jdhuff:	JPEG.h.jpeglib
o.jdhuff:	JPEG.h.jmorecfg
o.jdhuff:	JPEG.h.jpegint
o.jdhuff:	JPEG.h.jerror
o.jdsample:	JPEG.c.jdsample
o.jdsample:	JPEG.h.jinclude
o.jdsample:	JPEG.h.jconfig
o.jdsample:	JPEG.h.jpeglib
o.jdsample:	JPEG.h.jmorecfg
o.jdsample:	JPEG.h.jpegint
o.jdsample:	JPEG.h.jerror
o.jdcolor:	JPEG.c.jdcolor
o.jdcolor:	JPEG.h.jinclude
o.jdcolor:	JPEG.h.jconfig
o.jdcolor:	JPEG.h.jpeglib
o.jdcolor:	JPEG.h.jmorecfg
o.jdcolor:	JPEG.h.jpegint
o.jdcolor:	JPEG.h.jerror
o.jquant1:	JPEG.c.jquant1
o.jquant1:	JPEG.h.jinclude
o.jquant1:	JPEG.h.jconfig
o.jquant1:	JPEG.h.jpeglib
o.jquant1:	JPEG.h.jmorecfg
o.jquant1:	JPEG.h.jpegint
o.jquant1:	JPEG.h.jerror
o.jquant2:	JPEG.c.jquant2
o.jquant2:	JPEG.h.jinclude
o.jquant2:	JPEG.h.jconfig
o.jquant2:	JPEG.h.jpeglib
o.jquant2:	JPEG.h.jmorecfg
o.jquant2:	JPEG.h.jpegint
o.jquant2:	JPEG.h.jerror
o.jdmerge:	JPEG.c.jdmerge
o.jdmerge:	JPEG.h.jinclude
o.jdmerge:	JPEG.h.jconfig
o.jdmerge:	JPEG.h.jpeglib
o.jdmerge:	JPEG.h.jmorecfg
o.jdmerge:	JPEG.h.jpegint
o.jdmerge:	JPEG.h.jerror
o.djpeg:	JPEG.c.djpeg
o.djpeg:	JPEG.h.cdjpeg
o.djpeg:	JPEG.h.jinclude
o.djpeg:	JPEG.h.jconfig
o.djpeg:	JPEG.h.jpeglib
o.djpeg:	JPEG.h.jmorecfg
o.djpeg:	JPEG.h.jerror
o.djpeg:	JPEG.h.cderror
o.djpeg:	JPEG.h.cderror
o.djpeg:	JPEG.h.jversion
o.wrgif:	JPEG.c.wrgif
o.wrgif:	JPEG.h.cdjpeg
o.wrgif:	JPEG.h.jinclude
o.wrgif:	JPEG.h.jconfig
o.wrgif:	JPEG.h.jpeglib
o.wrgif:	JPEG.h.jmorecfg
o.wrgif:	JPEG.h.jerror
o.wrgif:	JPEG.h.cderror
o.wrppm:	JPEG.c.wrppm
o.wrppm:	JPEG.h.cdjpeg
o.wrppm:	JPEG.h.jinclude
o.wrppm:	JPEG.h.jconfig
o.wrppm:	JPEG.h.jpeglib
o.wrppm:	JPEG.h.jmorecfg
o.wrppm:	JPEG.h.jerror
o.wrppm:	JPEG.h.cderror
o.wrrle:	JPEG.c.wrrle
o.wrrle:	JPEG.h.cdjpeg
o.wrrle:	JPEG.h.jinclude
o.wrrle:	JPEG.h.jconfig
o.wrrle:	JPEG.h.jpeglib
o.wrrle:	JPEG.h.jmorecfg
o.wrrle:	JPEG.h.jerror
o.wrrle:	JPEG.h.cderror
o.wrtarga:	JPEG.c.wrtarga
o.wrtarga:	JPEG.h.cdjpeg
o.wrtarga:	JPEG.h.jinclude
o.wrtarga:	JPEG.h.jconfig
o.wrtarga:	JPEG.h.jpeglib
o.wrtarga:	JPEG.h.jmorecfg
o.wrtarga:	JPEG.h.jerror
o.wrtarga:	JPEG.h.cderror
o.wrbmp:	JPEG.c.wrbmp
o.wrbmp:	JPEG.h.cdjpeg
o.wrbmp:	JPEG.h.jinclude
o.wrbmp:	JPEG.h.jconfig
o.wrbmp:	JPEG.h.jpeglib
o.wrbmp:	JPEG.h.jmorecfg
o.wrbmp:	JPEG.h.jerror
o.wrbmp:	JPEG.h.cderror
o.rdcolmap:	JPEG.c.rdcolmap
o.rdcolmap:	JPEG.h.cdjpeg
o.rdcolmap:	JPEG.h.jinclude
o.rdcolmap:	JPEG.h.jconfig
o.rdcolmap:	JPEG.h.jpeglib
o.rdcolmap:	JPEG.h.jmorecfg
o.rdcolmap:	JPEG.h.jerror
o.rdcolmap:	JPEG.h.cderror
o.jcapi:	JPEG.c.jcapi
o.jcapi:	JPEG.h.jinclude
o.jcapi:	JPEG.h.jconfig
o.jcapi:	JPEG.h.jpeglib
o.jcapi:	JPEG.h.jmorecfg
o.jcapi:	JPEG.h.jpegint
o.jcapi:	JPEG.h.jerror
o.jcparam:	JPEG.c.jcparam
o.jcparam:	JPEG.h.jinclude
o.jcparam:	JPEG.h.jconfig
o.jcparam:	JPEG.h.jpeglib
o.jcparam:	JPEG.h.jmorecfg
o.jcparam:	JPEG.h.jpegint
o.jcparam:	JPEG.h.jerror
o.jdatadst:	JPEG.c.jdatadst
o.jdatadst:	JPEG.h.jinclude
o.jdatadst:	JPEG.h.jconfig
o.jdatadst:	JPEG.h.jpeglib
o.jdatadst:	JPEG.h.jmorecfg
o.jdatadst:	JPEG.h.jerror
o.jcmaster:	JPEG.c.jcmaster
o.jcmaster:	JPEG.h.jinclude
o.jcmaster:	JPEG.h.jconfig
o.jcmaster:	JPEG.h.jpeglib
o.jcmaster:	JPEG.h.jmorecfg
o.jcmaster:	JPEG.h.jpegint
o.jcmaster:	JPEG.h.jerror
o.jcmarker:	JPEG.c.jcmarker
o.jcmarker:	JPEG.h.jinclude
o.jcmarker:	JPEG.h.jconfig
o.jcmarker:	JPEG.h.jpeglib
o.jcmarker:	JPEG.h.jmorecfg
o.jcmarker:	JPEG.h.jpegint
o.jcmarker:	JPEG.h.jerror
o.jcmainct:	JPEG.c.jcmainct
o.jcmainct:	JPEG.h.jinclude
o.jcmainct:	JPEG.h.jconfig
o.jcmainct:	JPEG.h.jpeglib
o.jcmainct:	JPEG.h.jmorecfg
o.jcmainct:	JPEG.h.jpegint
o.jcmainct:	JPEG.h.jerror
o.jcprepct:	JPEG.c.jcprepct
o.jcprepct:	JPEG.h.jinclude
o.jcprepct:	JPEG.h.jconfig
o.jcprepct:	JPEG.h.jpeglib
o.jcprepct:	JPEG.h.jmorecfg
o.jcprepct:	JPEG.h.jpegint
o.jcprepct:	JPEG.h.jerror
o.jccoefct:	JPEG.c.jccoefct
o.jccoefct:	JPEG.h.jinclude
o.jccoefct:	JPEG.h.jconfig
o.jccoefct:	JPEG.h.jpeglib
o.jccoefct:	JPEG.h.jmorecfg
o.jccoefct:	JPEG.h.jpegint
o.jccoefct:	JPEG.h.jerror
o.jccolor:	JPEG.c.jccolor
o.jccolor:	JPEG.h.jinclude
o.jccolor:	JPEG.h.jconfig
o.jccolor:	JPEG.h.jpeglib
o.jccolor:	JPEG.h.jmorecfg
o.jccolor:	JPEG.h.jpegint
o.jccolor:	JPEG.h.jerror
o.jcsample:	JPEG.c.jcsample
o.jcsample:	JPEG.h.jinclude
o.jcsample:	JPEG.h.jconfig
o.jcsample:	JPEG.h.jpeglib
o.jcsample:	JPEG.h.jmorecfg
o.jcsample:	JPEG.h.jpegint
o.jcsample:	JPEG.h.jerror
o.jchuff:	JPEG.c.jchuff
o.jchuff:	JPEG.h.jinclude
o.jchuff:	JPEG.h.jconfig
o.jchuff:	JPEG.h.jpeglib
o.jchuff:	JPEG.h.jmorecfg
o.jchuff:	JPEG.h.jpegint
o.jchuff:	JPEG.h.jerror
o.jcdctmgr:	JPEG.c.jcdctmgr
o.jcdctmgr:	JPEG.h.jinclude
o.jcdctmgr:	JPEG.h.jconfig
o.jcdctmgr:	JPEG.h.jpeglib
o.jcdctmgr:	JPEG.h.jmorecfg
o.jcdctmgr:	JPEG.h.jpegint
o.jcdctmgr:	JPEG.h.jerror
o.jcdctmgr:	JPEG.h.jdct
o.jfdctfst:	JPEG.c.jfdctfst
o.jfdctfst:	JPEG.h.jinclude
o.jfdctfst:	JPEG.h.jconfig
o.jfdctfst:	JPEG.h.jpeglib
o.jfdctfst:	JPEG.h.jmorecfg
o.jfdctfst:	JPEG.h.jpegint
o.jfdctfst:	JPEG.h.jerror
o.jfdctfst:	JPEG.h.jdct
o.jfdctflt:	JPEG.c.jfdctflt
o.jfdctflt:	JPEG.h.jinclude
o.jfdctflt:	JPEG.h.jconfig
o.jfdctflt:	JPEG.h.jpeglib
o.jfdctflt:	JPEG.h.jmorecfg
o.jfdctflt:	JPEG.h.jpegint
o.jfdctflt:	JPEG.h.jerror
o.jfdctflt:	JPEG.h.jdct
o.jfdctint:	JPEG.c.jfdctint
o.jfdctint:	JPEG.h.jinclude
o.jfdctint:	JPEG.h.jconfig
o.jfdctint:	JPEG.h.jpeglib
o.jfdctint:	JPEG.h.jmorecfg
o.jfdctint:	JPEG.h.jpegint
o.jfdctint:	JPEG.h.jerror
o.jfdctint:	JPEG.h.jdct
o.cjpeg:	JPEG.c.cjpeg
o.cjpeg:	JPEG.h.cdjpeg
o.cjpeg:	JPEG.h.jinclude
o.cjpeg:	JPEG.h.jconfig
o.cjpeg:	JPEG.h.jpeglib
o.cjpeg:	JPEG.h.jmorecfg
o.cjpeg:	JPEG.h.jerror
o.cjpeg:	JPEG.h.cderror
o.cjpeg:	JPEG.h.cderror
o.cjpeg:	JPEG.h.jversion
o.rdppm:	JPEG.c.rdppm
o.rdppm:	JPEG.h.cdjpeg
o.rdppm:	JPEG.h.jinclude
o.rdppm:	JPEG.h.jconfig
o.rdppm:	JPEG.h.jpeglib
o.rdppm:	JPEG.h.jmorecfg
o.rdppm:	JPEG.h.jerror
o.rdppm:	JPEG.h.cderror
o.rdgif:	JPEG.c.rdgif
o.rdgif:	JPEG.h.cdjpeg
o.rdgif:	JPEG.h.jinclude
o.rdgif:	JPEG.h.jconfig
o.rdgif:	JPEG.h.jpeglib
o.rdgif:	JPEG.h.jmorecfg
o.rdgif:	JPEG.h.jerror
o.rdgif:	JPEG.h.cderror
o.rdtarga:	JPEG.c.rdtarga
o.rdtarga:	JPEG.h.cdjpeg
o.rdtarga:	JPEG.h.jinclude
o.rdtarga:	JPEG.h.jconfig
o.rdtarga:	JPEG.h.jpeglib
o.rdtarga:	JPEG.h.jmorecfg
o.rdtarga:	JPEG.h.jerror
o.rdtarga:	JPEG.h.cderror
o.rdrle:	JPEG.c.rdrle
o.rdrle:	JPEG.h.cdjpeg
o.rdrle:	JPEG.h.jinclude
o.rdrle:	JPEG.h.jconfig
o.rdrle:	JPEG.h.jpeglib
o.rdrle:	JPEG.h.jmorecfg
o.rdrle:	JPEG.h.jerror
o.rdrle:	JPEG.h.cderror
o.rdbmp:	JPEG.c.rdbmp
o.rdbmp:	JPEG.h.cdjpeg
o.rdbmp:	JPEG.h.jinclude
o.rdbmp:	JPEG.h.jconfig
o.rdbmp:	JPEG.h.jpeglib
o.rdbmp:	JPEG.h.jmorecfg
o.rdbmp:	JPEG.h.jerror
o.rdbmp:	JPEG.h.cderror
o.jutils:	JPEG.c.jutils
o.jutils:	JPEG.h.jinclude
o.jutils:	JPEG.h.jconfig
o.jutils:	JPEG.h.jpeglib
o.jutils:	JPEG.h.jmorecfg
o.jutils:	JPEG.h.jpegint
o.jutils:	JPEG.h.jerror
o.jerror:	JPEG.c.jerror
o.jerror:	JPEG.h.jinclude
o.jerror:	JPEG.h.jconfig
o.jerror:	JPEG.h.jpeglib
o.jerror:	JPEG.h.jmorecfg
o.jerror:	JPEG.h.jversion
o.jerror:	JPEG.h.jerror
o.jerror:	JPEG.h.jerror
o.jmemmgr:	JPEG.c.jmemmgr
o.jmemmgr:	JPEG.h.jinclude
o.jmemmgr:	JPEG.h.jconfig
o.jmemmgr:	JPEG.h.jpeglib
o.jmemmgr:	JPEG.h.jmorecfg
o.jmemmgr:	JPEG.h.jpegint
o.jmemmgr:	JPEG.h.jerror
o.jmemmgr:	JPEG.h.jmemsys
o.jmemmgr:	JPEG.h.jmemmgr
o.jmemnobs:	JPEG.c.jmemnobs
o.jmemnobs:	JPEG.h.jinclude
o.jmemnobs:	JPEG.h.jconfig
o.jmemnobs:	JPEG.h.jpeglib
o.jmemnobs:	JPEG.h.jmorecfg
o.jmemnobs:	JPEG.h.jpegint
o.jmemnobs:	JPEG.h.jerror
o.jmemnobs:	JPEG.h.jmemsys
o.jcomapi:	JPEG.c.jcomapi
o.jcomapi:	JPEG.h.jinclude
o.jcomapi:	JPEG.h.jconfig
o.jcomapi:	JPEG.h.jpeglib
o.jcomapi:	JPEG.h.jmorecfg
o.jcomapi:	JPEG.h.jpegint
o.jcomapi:	JPEG.h.jerror
o.JPEGprint:	c.JPEGprint
o.JPEGprint:	C:h.kernel
