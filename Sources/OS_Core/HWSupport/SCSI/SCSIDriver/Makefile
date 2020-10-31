# Makefile for SCSI Driver
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 25-May-94  AMcC         Created.
#

#
# Paths
#
EXP_HDR = <export$dir>

#
# Generic options:
#
MKDIR    = cdir
AS       = aasm
CP       = copy
RM       = remove
TOKENISE = tokenise

CFLAGS   = -c -depend !Depend -IC:
AFLAGS   = -depend !Depend -Stamp -quit -module
CPFLAGS  = ~cfr~v

TOKENS   = Hdr:Tokens

#
# Program specific options:
#
COMPONENT = SCSIDriver
LOG       = SCSILog
EXPORTS   = ${EXP_HDR}.SCSI

#
# Generic rules:
#
all: ${COMPONENT} ${LOG}
        @echo ${COMPONENT}: all built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

clean:
        ${RM} ${COMPONENT}
        ${RM} ${LOG}
        @echo ${COMPONENT}: cleaned

${COMPONENT}: s.SCSIDriver
        ${AS} ${AFLAGS} -from s.SCSIDriver -to $@

${LOG}: s.SCSILog
        ${AS} ${AFLAGS} -from s.SCSILog -to $@

${EXP_HDR}.SCSI: hdr.SCSI
        ${CP} hdr.SCSI $@ ${CPFLAGS}

# Dynamic dependencies:
