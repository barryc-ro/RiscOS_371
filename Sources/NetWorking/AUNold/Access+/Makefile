# Makefile for Access+
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 31-May-95  AMcC   Created

#
# Program specific options:
#
#COMPONENT  = Access+

# Generic options:
#
ATTR    = -attr
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

ACCESS_PLUS=\
 Access+.!Access+.!Help\
 Access+.!Access+.!Run\
 Access+.!Access+.!RunImage\
 Access+.!Access+.!Shares\
 Access+.!Access+.!Sprites\
 Access+.!Access+.!Sprites22\
 Access+.!Access+.Messages\
 Access+.!Access+.PINS\
 Access+.!Access+.Resources.StartImage\
 Access+.!Access+.Templates

ACCESS_CD=\
 Access+.!AccessCD.!Boot\
 Access+.!AccessCD.!Help\
 Access+.!AccessCD.!Run\
 Access+.!AccessCD.!RunCDFS\
 Access+.!AccessCD.!Sprites\
 Access+.!AccessCD.!Sprites22\
 Access+.!AccessCD.Config\
 Access+.!AccessCD.Resources.!RunImage\
 Access+.!AccessCD.Resources.Messages\
 Access+.!AccessCD.Resources.rm.CDCacheP\
 Access+.!AccessCD.Resources.Templates\
 Access+.!AccessCD.Resources.Utils.SetCache\
 Access+.!AccessCD.Resources.Utils.TestCDP\
 Access+.!AccessCD.sharecd

FILES=\
 Network.Share+\
 Access+.ReadMe\
 ${ACCESS_PLUS}\
 ${ACCESS_CD}

#
# GENERIC RULES
#                  
install: install_${COMPONENT}
    @echo $(COMPONENT): installed

install_Share+:
    ${CP} Network ${INSTDIR}.Network ${CPFLAGS}
    ${ATTR} -directories +wr ${INSTDIR}.Network
    ${ATTR} -files +or +ow +wr -ww ${INSTDIR}.Network

install_Access+:
    ${CP} Access+ ${INSTDIR}.Access+ ${CPFLAGS}
    ${ATTR} -directories +wr ${INSTDIR}.Access+
    ${ATTR} -files +or +ow +wr -ww ${INSTDIR}.Access+

#---------------------------------------------------------------------------
# Dynamic dependencies:
