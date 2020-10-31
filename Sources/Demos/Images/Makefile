# Makefile for Images
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 18-Nov-94  AMcC   Updated for Black build
#

#
# Program specific options:
#
COMPONENT  = Images
LDIR       = ${LOCALE}

# Generic options:
#
MKDIR   = cdir
CP      = copy
RM      = remove
SQUISH  = squish
WIPE    = -wipe

CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

PICCIES=

PICCIES1=\
 00-49.key00-24\
 00-49.key25-49\
 00-49.sa00\
 00-49.sa01\
 00-49.sa02\
 00-49.sa03\
 00-49.sa04\
 00-49.sa05\
 00-49.sa06\
 00-49.sa07\
 00-49.sa08\
 00-49.sa09\
 00-49.sa10\
 00-49.sa11\
 00-49.sa12\
 00-49.sa13\
 00-49.sa14\
 00-49.sa15\
 00-49.sa16\
 00-49.sa17\
 00-49.sa18\
 00-49.sa19\
 00-49.sa20\
 00-49.sa21\
 00-49.sa22\
 00-49.sa23\
 00-49.sa24\
 00-49.sa25\
 00-49.sa26\
 00-49.sa27\
 00-49.sa28\
 00-49.sa29\
 00-49.sa30\
 00-49.sa31\
 00-49.sa32\
 00-49.sa33\
 00-49.sa34\
 00-49.sa35\
 00-49.sa36\
 00-49.sa37\
 00-49.sa38\
 00-49.sa39\
 00-49.sa40\
 00-49.sa41\
 00-49.sa42\
 00-49.sa43\
 00-49.sa44\
 00-49.sa45\
 00-49.sa46\
 00-49.sa47\
 00-49.sa48\
 00-49.sa49

PICCIES2=\
 50-99.Key50-74\
 50-99.Key75-99\
 50-99.sa50\
 50-99.sa51\
 50-99.sa52\
 50-99.sa53\
 50-99.sa54\
 50-99.sa55\
 50-99.sa56\
 50-99.sa57\
 50-99.sa58\
 50-99.sa59\
 50-99.sa60\
 50-99.sa61\
 50-99.sa62\
 50-99.sa63\
 50-99.sa64\
 50-99.sa65\
 50-99.sa66\
 50-99.sa67\
 50-99.sa68\
 50-99.sa69\
 50-99.sa70\
 50-99.sa71\
 50-99.sa72\
 50-99.sa73\
 50-99.sa74\
 50-99.sa75\
 50-99.sa76\
 50-99.sa77\
 50-99.sa78\
 50-99.sa79\
 50-99.sa80\
 50-99.sa81\
 50-99.sa82\
 50-99.sa83\
 50-99.sa84\
 50-99.sa85\
 50-99.sa86\
 50-99.sa87\
 50-99.sa88\
 50-99.sa89\
 50-99.sa90\
 50-99.sa91\
 50-99.sa92\
 50-99.sa93\
 50-99.sa94\
 50-99.sa95\
 50-99.sa96\
 50-99.sa97\
 50-99.sa98\
 50-99.sa99

TEAMPIC=Team.Picture

DOCS   =$(LDIR).ReadMe $(LDIR).Team.ReadMe
FILES  =$(PICCIES1) $(PICCIES2) $(TEAMPIC) $(DOCS)

#
# GENERIC RULES
#                  
all: $(FILES)
          @echo $(COMPONENT): all build complete

install: $(FILES)
         ${CP} $(LDIR).ReadMe ${INSTDIR}.ReadMe ${CPFLAGS}
         ${CP} 00-49 ${INSTDIR}.00-49 ${CPFLAGS}
         ${CP} 50-99 ${INSTDIR}.50-99 ${CPFLAGS}
         ${CP} Team  ${INSTDIR}.Team  ${CPFLAGS}
         ${CP} $(LDIR).Team.ReadMe ${INSTDIR}.Team.ReadMe ${CPFLAGS}
         -attr -directories +wr ${INSTDIR}
         -attr -files +or +ow +wr -ww ${INSTDIR}
         @echo $(COMPONENT): installed

clean:
         @echo $(COMPONENT): cleaned

#---------------------------------------------------------------------------
# Dynamic dependencies:
