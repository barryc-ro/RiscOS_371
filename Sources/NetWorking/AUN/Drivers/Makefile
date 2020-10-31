# Makefile for Access+
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 15-Jul-96  KJB    Created

#
# Program specific options:
#
#COMPONENT  = Drivers

# Generic options:
#
ATTR    = -attr
MKDIR   = cdir
CP      = copy
RM      = remove
WIPE    = -wipe

CPFLAGS = ~cfr~v
WFLAGS  = ~c~v

FILES=\
 Network.Ether1\
 Network.Ether2\
 Network.Ether3-16\
 Network.EtherB\
 Network.EtherH16\
 Network.EtherO

#
# GENERIC RULES
#                  
install: 
    ${CP} Network ${INSTDIR}.Network ${CPFLAGS}
    ${ATTR} -directories +wr ${INSTDIR}.Network
    ${ATTR} -files +or +ow +wr -ww ${INSTDIR}.Network

#---------------------------------------------------------------------------
# Dynamic dependencies:
