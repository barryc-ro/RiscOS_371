# Makefile for SprExtend
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name    Description
# ----       ----    -----------
# 25-May-94  AMcC    Created.
# 12-Aug-94  AMcC    Updated for modified SpriteExtend (JPEG support)
# 29-Oct-94  AMcC    Exports hdr.SprExtend (SWI defs)
#                    Data file now called CFSIjpeg (was CFSI-jpeg)
#                    - exported to ChangeFSI at install time
# 01-Feb-95  GPS     Now compiles with cc505
# 13-Feb-95  GPS     CFSIjpeg now compiles with cc505
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
AASM    = aasm
CC      = cc
CP      = copy
LINK    = link
# -d does debug tables
MKDIR   = cdir
OBJASM  = objasm
RM      = remove
WIPE    = -wipe
SED     = Sed

# To switch between making debugging and non-debugging versions of SprExtend:
#   change the #define of DEBUG at the top of c.PutScaled
#   change the SETL of 'debug' in sources.SprExtend.

ASFLAGS  = -depend !Depend -Stamp -quit -module
OBJFLAGS = -depend !Depend -Stamp -quit
CFLAGS   = -depend !Depend ${INCLUDES} ${DFLAGS}
DFLAGS   = -DRISCOS -DASMHUFF
#DFLAGS   = -DRISCOS -DASMHUFF -DDEBUG
CPFLAGS  = ~cfr~v
WFLAGS   = ~c~v

INCLUDES = -IC:

#
# Libraries
#
CLIB = CLIB:o.stubs

#
# Program specific options:
#
COMPONENT = SprExtend
SOURCE    = Sources.SprExtend
TARGET    = rm.SprExtend
LOCALMSG  = rm.SprExtendM
EXPORTS   = ${EXP_HDR}.SprExtend

SFILES =\
 s.jhdr\
 s.putscaled\
 s.stdpalette\
 s.yuvtabs

# Extra utilites (generate assembler code)
MAKEJHDR   = utils.makejhdr
GENPALETTE = utils.genpalette
GENYUVTABS = utils.genyuvtabs

# Needed for ChangeFSI
CFSI-JPEG  = data.CFSIjpeg

#
# Rule patterns
#
.SUFFIXES: .o .c .sources

.c.o:;       ${CC} -c ${CFLAGS} -o $@ $<
.sources.o:; ${OBJASM} ${OBJFLAGS} -from $< -to $@

#
# Rules:
#
all: ${CFSI-JPEG} ${LOCALMSG}
        @echo ${COMPONENT}: all built

install: ${CFSI-JPEG}
        ${CP} ${CFSI-JPEG} ${INSTDIR}.CFSIjpeg ${CPFLAGS}
        Access ${INSTDIR}.CFSIjpeg lr/r
        @echo ${COMPONENT}: CFSIjpeg file installed

cfsi-jpeg: ${CFSI-JPEG}
        @echo ${COMPONENT}: CFSIjpeg file generated

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
        ${RM} ${LOCALMSG}
        ${RM} ${GENPALETTE}
        ${RM} ${GENYUVTABS}
        ${RM} ${MAKEJHDR}
        ${RM} ${CFSI-JPEG}
        ${WIPE} o.* ${WFLAGS}
        ${WIPE} s.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned

resources:
        ${MKDIR} ${RESDIR}.${COMPONENT}
        ${CP} Resources.${LOCALE}.Messages  ${RESDIR}.${COMPONENT}.Messages  ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} ${SFILES}
        ${AASM} ${ASFLAGS} -From ${SOURCE} -To $@

# Get the Messages from somewhere other than Resources:$.Resources.SprExtend
${LOCALMSG}: Sources.LocalMsgs ${SFILES}
        ${AASM} ${ASFLAGS} -From Sources.LocalMsgs -To $@

# Export the SWI definitions to Hdr:
${EXP_HDR}.SprExtend: hdr.SprExtend
        ${CP} hdr.SprExtend $@ ${CPFLAGS}
#
# Generate the SFILES
#
s.putscaled: c.putscaled
        ${CC} -s ${CFLAGS} -ff -zps1 -DEMBED c.putscaled
        @echo ${COMPONENT}: making s.putscaled aasm compatible
        ${SED} s/__rt_sdiv/|__rt_sdiv|/g < s.putscaled > s.temp
        ${SED} s/_swix/|_swix|/g < s.temp > s.putscaled

s.yuvtabs: ${GENYUVTABS}
        ${GENYUVTABS} > s.yuvtabs

s.stdpalette: ${GENPALETTE}
        ${GENPALETTE} > s.stdpalette

s.jhdr: ${MAKEJHDR}
        ${MAKEJHDR} > s.jhdr

${GENPALETTE}: o.genpalette ${CLIB}
        ${LINK} -o $@ o.genpalette ${CLIB}

${GENYUVTABS}: o.genyuvtabs ${CLIB}
        ${LINK} -o $@ o.genyuvtabs ${CLIB}

${MAKEJHDR}: o.makejhdr ${CLIB}
        ${LINK} -o $@ o.makejhdr ${CLIB}
#
# For ChangeFSI:
#
${CFSI-JPEG}: Sources.cfsi-jpeg s.jhdr s.rojpeg s.stdpalette
        ${AASM} ${ASFLAGS} -From Sources.cfsi-jpeg -To $@
        SetType $@ Data

# needed for the ChangeFSI inclusion:
s.rojpeg: c.rojpeg
        ${CC} -s ${CFLAGS} -ff -zps1 -DEMBED -DCFSI c.rojpeg
        ${SED} s/__rt_sdiv/|__rt_sdiv|/g < s.rojpeg > s.temp
        ${CP} s.temp s.rojpeg ${CPFLAGS}
#        Run w.ZapS-ROJ

#
# Other bits:
#
j2s: o.j2s o.jdhuff o.jrevdct o.jcconv o.diffuse
        ${LINK} -o j2s o.j2s o.jdhuff o.jrevdct o.jcconv o.diffuse ${CLIB}

o.diffuse: sources.diffuseo s.stdpalette
        ${OBJASM} ${OBJFLAGS} -from sources.diffuseo -to $@

o.jcconv: sources.jcconvo s.yuvtabs
        ${OBJASM} ${OBJFLAGS} -from sources.jcconvo -to $@

o.jdhuff: sources.jdhuffo s.jhdr
        ${OBJASM} ${OBJFLAGS} -from sources.jdhuffo -to $@

o.jrevdct: sources.jrevdcto
        ${OBJASM} ${OBJFLAGS} -from sources.jrevdcto -to $@

put: o.put
        ${LINK} -o put o.put ${CLIB}

jput: o.jput
        ${LINK} -o jput o.jput ${CLIB}

tdct: o.testdct o.idcto
        ${LINK} -o tdct o.testdct o.idcto ${CLIB}

o.swiv: sources.swiv

# Dynamic dependencies:
data.CFSI-jpeg: sources.csupport
data.CFSI-jpeg: sources.jdhuff
data.CFSI-jpeg: s.jhdr
data.CFSI-jpeg: sources.jrevdct
data.CFSI-jpeg: sources.jcconv
data.CFSI-jpeg: sources.diffuse
data.CFSI-jpeg: s.stdpalette
data.CFSI-jpeg: s.rojpeg
rm.SprExtend: Hdr:ListOpts
rm.SprExtend: Hdr:Macros
rm.SprExtend: Hdr:System
rm.SprExtend: Hdr:SWIs
rm.SprExtend: Hdr:CPU.Generic26
rm.SprExtend: Hdr:IO.GenericIO
rm.SprExtend: Hdr:RISCOS
rm.SprExtend: Hdr:ModHand
rm.SprExtend: Hdr:Services
rm.SprExtend: Hdr:VduExt
rm.SprExtend: Hdr:FSNumbers
rm.SprExtend: Hdr:NewErrors
rm.SprExtend: Hdr:NDRDebug
rm.SprExtend: Hdr:Sprite
rm.SprExtend: Hdr:ColourTran
rm.SprExtend: Hdr:PublicWS
rm.SprExtend: Hdr:Draw
rm.SprExtend: Hdr:ExtraLong
rm.SprExtend: Hdr:MsgTrans
rm.SprExtend: Hdr:Proc
rm.SprExtend: Hdr:HostFS
rm.SprExtend: Hdr:Debug
rm.SprExtend: Hdr:HostDebug
rm.SprExtend: Version
rm.SprExtend: Hdr:PDriver
rm.SprExtend: Sources.SWIs
rm.SprExtend: Sources.SprAdjSize
rm.SprExtend: Sources.SprTrans
rm.SprExtend: Sources.MsgCode
rm.SprExtend: Sources.PutScaled
rm.SprExtend: sources.CSupport
rm.SprExtend: S.PutScaled
rm.SprExtend: sources.jdhuff
rm.SprExtend: s.jhdr
rm.SprExtend: sources.jrevdct
rm.SprExtend: s.yuvtabs
rm.SprExtend: sources.jcconv
rm.SprExtend: sources.diffuse
rm.SprExtend: sources.swiv2
o.genpalette:	c.genpalette
o.putscaled:	c.putscaled
o.putscaled:	c.rojpeg
o.putscaled:	h.rojpeg
o.putscaled:	h.jinclude
o.putscaled:	h.jconfig
o.putscaled:	h.jpegdata
o.putscaled:	h.swis
o.putscaled:	h.kernel
o.putscaled:	c.jrdjfif
o.putscaled:	h.jinclude
o.putscaled:	c.jdhuff
o.putscaled:	h.jinclude
o.putscaled:	c.jcconv
o.putscaled:	c.SpriteOp
o.makejhdr:	c.makejhdr
o.makejhdr:	h.jinclude
o.makejhdr:	h.jconfig
o.makejhdr:	h.jpegdata
o.genyuvtabs:	c.genyuvtabs
data.CFSIjpeg: sources.csupport
data.CFSIjpeg: sources.jdhuff
data.CFSIjpeg: s.jhdr
data.CFSIjpeg: sources.jrevdct
data.CFSIjpeg: sources.jcconv
data.CFSIjpeg: sources.diffuse
data.CFSIjpeg: s.rojpeg
o.rojpeg:	c.rojpeg
o.rojpeg:	h.rojpeg
o.rojpeg:	h.jinclude
o.rojpeg:	h.jconfig
o.rojpeg:	h.jpegdata
o.rojpeg:	h.swis
o.rojpeg:	h.kernel
o.rojpeg:	c.jrdjfif
o.rojpeg:	h.jinclude
o.rojpeg:	c.jdhuff
o.rojpeg:	h.jinclude
o.rojpeg:	c.jcconv
o.rojpeg:	c.SpriteOp
rm.SprExtendM: Sources.SprExtend
rm.SprExtendM: Hdr:ListOpts
rm.SprExtendM: Hdr:Macros
rm.SprExtendM: Hdr:System
rm.SprExtendM: Hdr:SWIs
rm.SprExtendM: Hdr:CPU.Generic26
rm.SprExtendM: Hdr:IO.GenericIO
rm.SprExtendM: Hdr:RISCOS
rm.SprExtendM: Hdr:ModHand
rm.SprExtendM: Hdr:Services
rm.SprExtendM: Hdr:VduExt
rm.SprExtendM: Hdr:FSNumbers
rm.SprExtendM: Hdr:NewErrors
rm.SprExtendM: Hdr:NDRDebug
rm.SprExtendM: Hdr:Sprite
rm.SprExtendM: Hdr:ColourTran
rm.SprExtendM: Hdr:PublicWS
rm.SprExtendM: Hdr:Draw
rm.SprExtendM: Hdr:ExtraLong
rm.SprExtendM: Hdr:MsgTrans
rm.SprExtendM: Hdr:Proc
rm.SprExtendM: Hdr:HostFS
rm.SprExtendM: Hdr:Debug
rm.SprExtendM: Hdr:HostDebug
rm.SprExtendM: Version
rm.SprExtendM: Hdr:PDriver
rm.SprExtendM: Sources.SWIs
rm.SprExtendM: Sources.SprAdjSize
rm.SprExtendM: Sources.SprTrans
rm.SprExtendM: Sources.MsgCode
rm.SprExtendM: Sources.PutScaled
rm.SprExtendM: sources.CSupport
rm.SprExtendM: S.PutScaled
rm.SprExtendM: sources.jdhuff
rm.SprExtendM: s.jhdr
rm.SprExtendM: sources.jrevdct
rm.SprExtendM: s.yuvtabs
rm.SprExtendM: sources.jcconv
rm.SprExtendM: sources.diffuse
rm.SprExtendM: sources.swiv2
