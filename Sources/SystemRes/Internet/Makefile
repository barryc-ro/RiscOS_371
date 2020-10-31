# Makefile for Scrap
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date           Name   Description
# ----           ----   -----------
# 03-Jul-96      KJB    Derived from Scrap makefile
#

#
# Program specific options:
#
COMPONENT  = Internet
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
MKDIR   = cdir
ATTR    = -attr
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES=\
 ${RDIR}.!Boot\
 ${LDIR}.!Help\
 ${RDIR}.!Run\
 ${RDIR}.!Sprites\
 ${RDIR}.!Sprites22\
 ${RDIR}.bin.ARP\
 ${RDIR}.bin.IfConfig\
 ${RDIR}.bin.InetStat\
 ${RDIR}.bin.Ping\
 ${RDIR}.bin.RMFind\
 ${RDIR}.bin.Route\
 ${RDIR}.bin.ShowStat\
 ${RDIR}.bin.Sysctl\
 ${RDIR}.bin.X\
 ${RDIR}.files.AUNMap\
 ${RDIR}.files.Hosts\
 ${RDIR}.files.Networks\
 ${RDIR}.files.Protocols\
 ${RDIR}.files.Services\
 ${RDIR}.utils.BootNet\
 ${RDIR}.utils.CheckMem\
 ${RDIR}.utils.NewFiler\
 ${RDIR}.utils.ReadCMOSIP\
 ${RDIR}.utils.TriggerCBs

#
# Main rules:
#
all: ${FILES}
        @echo ${COMPONENT}: All built (Disc)

install: ${FILES}
        ${MKDIR} ${INSTDIR}
        |
        ${CP} ${RDIR}.!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
        ${CP} ${LDIR}.!Help      ${INSTDIR}.!Help      ${CPFLAGS}
        ${CP} ${RDIR}.!Run       ${INSTDIR}.!Run       ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
        ${CP} ${RDIR}.!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
        ${CP} ${RDIR}.bin        ${INSTDIR}.bin        ${CPFLAGS}
        ${CP} ${RDIR}.files      ${INSTDIR}.files      ${CPFLAGS}
        ${CP} ${RDIR}.utils      ${INSTDIR}.utils      ${CPFLAGS}
        |
        ${ATTR} -directories +wr -ww ${INSTDIR}
        ${ATTR} -files +or +ow +wr -ww ${INSTDIR}
        |
        @echo ${COMPONENT}: All installed (Disc)

clean:
        @echo ${COMPONENT}: cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
