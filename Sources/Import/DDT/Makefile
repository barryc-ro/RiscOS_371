# Makefile for DDT
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 12-Oct-94  AMcC         Created.
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
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v

#
# Program specific options:
#
COMPONENT = DDT
EXPORTS   = ${EXP_HDR}.DDT

#
# Generic rules:
#
export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

${EXP_HDR}.DDT: hdr.DDT
        ${CP} hdr.DDT $@ ${CPFLAGS}

# Dynamic dependencies:
