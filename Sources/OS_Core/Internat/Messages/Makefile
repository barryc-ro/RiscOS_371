# Makefile for Messages module
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name         Description
# ----       ----         -----------
# 02-Jun-94  AMcC         Created.
# 08-Dec-94  AMcC         Adjust rules and dependencies so that
#                         tokens don't need to be generated every time
#                         - remove data.Dictionary to regenerate tokens
#

#
# Generic options:
#
AS      = aasm
CP      = copy
MKDIR   = cdir
RM      = remove
WIPE    = -wipe
MAKE    = amu

CCFLAGS = -c -depend !Depend -IC:
ASFLAGS = -depend !Depend -Stamp -quit -module
CPFLAGS = ~cfr~v
TOUCH   = create
WFLAGS  = ~cr~v

#
# Program specific options:
#
COMPONENT = Messages
SOURCE    = s.Messages
TARGET    = rm.Messages
PROCESSDIR= Resources
LDIR      = ${LOCALE}
RESDIR    = <resource$dir>
UTILS     = Utils
DATA      = Data
# Note: RESDATA mustn't be in PROCESSDIR !!
RESDATA   = ${DATA}.Data
HELPTAGS  = ${DATA}.HelpTags
HELPMESS  = ${DATA}.HelpMess
HELPTOKENS= ${DATA}.HelpTokens
DICTTAGS  = ${DATA}.DictTags
DICTMESS  = ${DATA}.DictMess
DICTTOKENS= ${DATA}.DictTokens
DICTIONARY= ${DATA}.Dictionary

MINDICT   = ${DATA}.MinDict

#
# Utility programs:
#
TAGEXT  = ${UTILS}.TagExtract
MSGEXT  = ${UTILS}.MsgExt
MSGTOK  = ${UTILS}.MsgTok
TOKGEN  = ${UTILS}.TokGen
MSGEXT2 = ${UTILS}.MsgExt2
MSGTOK2 = ${UTILS}.MsgTok2
TOKGEN2 = ${UTILS}.TokGen2
SCANRES = ${UTILS}.ScanRes

#
# Generic rules:
#
rom: ${TARGET}
        @echo ${COMPONENT}: module built

export: ${EXPORTS}
        @echo ${COMPONENT}: export complete

install_rom: ${TARGET}
        ${CP} ${TARGET} ${INSTDIR}.${COMPONENT} ${CPFLAGS}
        @echo ${COMPONENT}: rom module installed

clean:
        ${RM} ${TARGET}
        ${RM} ${RESDATA}
        ${RM} ${DATA}.Tokenised
        ${RM} ${HELPTAGS}
        ${RM} ${DICTTAGS}
        ${WIPE} Resources.* ${WFLAGS}
        @echo ${COMPONENT}: cleaned (Dictionary & HelpTokens not removed)

#
# Clean_all: removes Dictionary and HelpTokens and ${LOCALE}.*
#
clean_all:
        ${RM} ${TARGET}
        ${RM} ${RESDATA}
        ${RM} ${DATA}.Tokenised
        ${RM} ${HELPTAGS}
        ${RM} ${HELPMESS}
        ${RM} ${HELPTOKENS}
        ${RM} ${DICTTAGS}
        ${RM} ${DICTMESS}
        ${RM} ${DICTTOKENS}
        ${RM} ${DICTIONARY}
        ${WIPE} Resources.* ${WFLAGS}
        @echo ${COMPONENT}: all cleaned

resources:
        ${MKDIR} ${RESDIR}.Resources.Global
        ${CP} Global.${LOCALE}.Messages ${RESDIR}.Resources.Global.Messages ${CPFLAGS}
        @echo ${COMPONENT}: resource files copied

${TARGET}: ${SOURCE} ${DATA}.Tokenised
        ${SCANRES} ${PROCESSDIR} ${RESDATA}
        set resdata ${RESDATA}
        ${AS} ${ASFLAGS} -To $@ -From ${SOURCE}
        unset resdata

#
# Tokenise the Messages file using Help and Dictionary Tokens
#
${DATA}.Tokenised: ${DICTIONARY} ${HELPTOKENS} ${HELPTAGS}
        Print ${HELPTOKENS} { >> ${PROCESSDIR}.Resources.Help.Messages }
        ${MSGTOK} ${HELPTOKENS} ${HELPTAGS}
        ${CP} ${DICTIONARY} ${PROCESSDIR}.Resources.Kernel.Dictionary ${CPFLAGS}
        ${MSGTOK2} ${DICTTOKENS} ${DICTTAGS}
        ${TOUCH} ${DATA}.Tokenised; settype ${DATA}.Tokenised fff

#
# Copy Local Resources, then extract Help and Dictionary token tags
#
${HELPTAGS}:
        @echo Copying ${LOCALE} Resources to Resources directory for tokenising ...
        ${CP} ${LOCALE} Resources ${CPFLAGS}
        ${TAGEXT} ${PROCESSDIR} ${DICTTAGS} ${HELPTAGS}

#
# Help tokens
#
${HELPTOKENS}:
        ${MSGEXT} ${HELPMESS} ${HELPTAGS}
        ${TOKGEN} ${HELPMESS} ${HELPTOKENS}

#
# Use minimum Dictionary tokens:
#
#${DICTIONARY}: ${DATA}.MinDict
#        ${CP} ${DATA}.MinDict  ${DICTIONARY} ${CPFLAGS}
#        ${CP} ${DATA}.MinDictT ${DICTTOKENS}  ${CPFLAGS}

#
# Use optimal Dictionary tokens:
#
${DICTIONARY}:
        ${MSGEXT2} ${DICTMESS} ${DICTTAGS}
        ${TOKGEN2} ${DICTMESS} ${DICTTOKENS} ${DICTIONARY}

${TAGEXT}:
        Dir ${UTILS}
        ${MAKE}
        Up

# Dynamic dependencies:
rm.Morris2.Messages: Hdr:ListOpts
rm.Morris2.Messages: Hdr:Macros
rm.Morris2.Messages: Hdr:System
rm.Morris2.Messages: Hdr:SWIs
rm.Morris2.Messages: Hdr:CPU.Generic26
rm.Morris2.Messages: Hdr:IO.GenericIO
rm.Morris2.Messages: Hdr:RISCOS
rm.Morris2.Messages: Hdr:ModHand
rm.Morris2.Messages: Hdr:Services
rm.Morris2.Messages: Hdr:Proc
rm.Morris2.Messages: Hdr:ResourceFS
rm.Morris2.Messages: Version
rm.Morris2.Messages: Hdr:NDRDebug
rm.Morris4.Messages: Hdr:ListOpts
rm.Morris4.Messages: Hdr:Macros
rm.Morris4.Messages: Hdr:System
rm.Morris4.Messages: Hdr:SWIs
rm.Morris4.Messages: Hdr:CPU.Generic26
rm.Morris4.Messages: Hdr:IO.GenericIO
rm.Morris4.Messages: Hdr:RISCOS
rm.Morris4.Messages: Hdr:ModHand
rm.Morris4.Messages: Hdr:Services
rm.Morris4.Messages: Hdr:Proc
rm.Morris4.Messages: Hdr:ResourceFS
rm.Morris4.Messages: Version
rm.Morris4.Messages: Hdr:NDRDebug
rm.Messages: Hdr:ListOpts
rm.Messages: Hdr:Macros
rm.Messages: Hdr:System
rm.Messages: Hdr:SWIs
rm.Messages: Hdr:CPU.Generic26
rm.Messages: Hdr:IO.GenericIO
rm.Messages: Hdr:RISCOS
rm.Messages: Hdr:ModHand
rm.Messages: Hdr:Services
rm.Messages: Hdr:Proc
rm.Messages: Hdr:ResourceFS
rm.Messages: Version
rm.Messages: Hdr:NDRDebug
