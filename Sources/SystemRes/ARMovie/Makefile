# Makefile for ARMovie
#
# ***********************************
# ***    C h a n g e   L i s t    ***
# ***********************************
# Date       Name   Description
# ----       ----   -----------
# 17-Nov-94  AMcC   Updated for Black build
# 08-Mar-95  AMcC   Added lines to install 16-bit Sound directory
# 22-Aug-96  MJS    additions to bring into line with 3.6 disc build release 5
#

#
# Program specific options:
#
COMPONENT  = ARMovie
APP        = !${COMPONENT}
RDIR       = Resources
LDIR       = ${RDIR}.${LOCALE}
INSTDIR    = ${INSTDIR}.${APP}

# Generic options:
#
ATTR    = -attr
MKDIR   = cdir
CP      = copy
RM      = remove
SQUISH  = squish
WIPE    = -wipe

CPFLAGS = ~cfr~v
SQFLAGS = -nolist
WFLAGS  = ~c~v

FILES  =\
 $(RDIR).!Boot\
 $(LDIR).!Help\
 $(RDIR).!Run\
 $(RDIR).!Sprites\
 $(RDIR).!Sprites22\
 $(RDIR).Access\
 $(RDIR).Default\
 $(RDIR).Player\
 $(RDIR).Sprites\
 $(RDIR).Sprites22\
 $(LDIR).Messages\
 $(RDIR).SetSndDir

FILESDC=\
 $(RDIR).Decomp2.MakeDecomp\
 $(RDIR).Decomp2.Info\
 $(RDIR).Decomp2.DecompresH\
 $(RDIR).Decomp2.Decompress\
 $(RDIR).Decomp3.MakeDecomp\
 $(RDIR).Decomp3.Info\
 $(RDIR).Decomp3.DecompresH\
 $(RDIR).Decomp3.Decompress\
 $(RDIR).Decomp4.MakeDecomp\
 $(RDIR).Decomp4.Info\
 $(RDIR).Decomp4.DecompresH\
 $(RDIR).Decomp4.Decompress\
 $(RDIR).Decomp5.MakeDecomp\
 $(RDIR).Decomp5.Info\
 $(RDIR).Decomp5.DecompresH\
 $(RDIR).Decomp5.Decompress\
 $(RDIR).Decomp6.MakeDecomp\
 $(RDIR).Decomp6.Info\
 $(RDIR).Decomp6.DecompresH\
 $(RDIR).Decomp6.Decompress\
 $(RDIR).Decomp7.BatchComp\
 $(RDIR).Decomp7.Info\
 $(RDIR).Decomp7.Decompress\
 $(RDIR).Decomp8.Makedecomp\
 $(RDIR).Decomp8.Decomp24\
 $(RDIR).Decomp8.DecompresH\
 $(RDIR).Decomp8.Decompress\
 $(RDIR).Decomp8.Info\
 $(RDIR).Decomp9.Makedecomp\
 $(RDIR).Decomp9.Decomp24\
 $(RDIR).Decomp9.DecompresH\
 $(RDIR).Decomp9.Decompress\
 $(RDIR).Decomp9.Info\
 $(RDIR).Decomp17.BatchComp\
 $(RDIR).Decomp17.Dec16\
 $(RDIR).Decomp17.DecompresB\
 $(RDIR).Decomp17.DecompresH\
 $(RDIR).Decomp17.Decompress\
 $(RDIR).Decomp17.Info

FILESTOOLS=\
 $(RDIR).Documents.AE7doc\
 $(RDIR).Documents.codecIf\
 $(RDIR).Documents.DecompIf\
 $(RDIR).Documents.Extract\
 $(RDIR).Documents.Join\
 $(RDIR).Documents.PrefBig\
 $(RDIR).Documents.ProgIf\
 $(RDIR).Documents.ToCapture\
 $(RDIR).Documents.ToUseSound\
 $(RDIR).Tools.Extract\
 $(RDIR).Tools.Join\
 $(RDIR).Tools.MakeCircle\
 $(RDIR).Tools.MakeScale\
 $(RDIR).Tools.MakeSplit\
 $(RDIR).Tools.MakeZoom

FILESML=\
 $(RDIR).MovingLine.8DefCol\
 $(RDIR).MovingLine.8rgb11\
 $(RDIR).MovingLine.8rgb22\
 $(RDIR).MovingLine.8yuv11\
 $(RDIR).MovingLine.8yuv22\
 $(RDIR).MovingLine.16yuv\
 $(RDIR).MovingLine.32yuv\
 $(RDIR).MovingLine.BatchComp\
 $(RDIR).MovingLine.Info\
 $(RDIR).MovingLine.Make4col11\
 $(RDIR).MovingLine.Make8col11\
 $(RDIR).MovingLine.Decompress\
 $(RDIR).MovingLine.SoundA4\
 $(RDIR).MovingLine.SoundA4x2\
 $(RDIR).MovingLine.SoundE8\
 $(RDIR).MovingLine.SoundE8x2\
 $(RDIR).MovingLine.SoundS16\
 $(RDIR).MovingLine.SoundS16x2\
 $(RDIR).MovingLine.SoundS8\
 $(RDIR).MovingLine.SoundS8x2\
 $(RDIR).MovingLine.SoundU8\
 $(RDIR).MovingLine.SoundU8x2\
 $(RDIR).MovingLine.adpcm.Playx2\
 $(RDIR).MovingLine.adpcm.Play\
 $(RDIR).MovingLine.adpcm.Info

FILES3=\
 $(RDIR).Trajectory.Bounce\
 $(RDIR).Trajectory.RollBFilm\
 $(RDIR).Trajectory.RollFilm\
 $(RDIR).Trajectory.RollTFilm\
 $(RDIR).Trajectory.ScaleUp\
 $(RDIR).Trajectory.ZoomUp\
 $(RDIR).Shapes.Circle\
 $(RDIR).Shapes.TallFilm.Film136\
 $(RDIR).Shapes.TallFilm.Film128\
 $(RDIR).Shapes.TallFilm.Film120\
 $(RDIR).Shapes.TallFilm.Film112\
 $(RDIR).Shapes.TallFilm.Film104\
 $(RDIR).Shapes.TallFilm.Film96\
 $(RDIR).Shapes.TallFilm.Film88\
 $(RDIR).Shapes.TallFilm.Film80\
 $(RDIR).Shapes.TallFilm.Film72\
 $(RDIR).Shapes.TallFilm.Film64\
 $(RDIR).Shapes.TallFilm.Film56\
 $(RDIR).Shapes.TallFilm.Film48\
 $(RDIR).Shapes.TallFilm.Film40\
 $(RDIR).Shapes.TallFilm.Film32\
 $(RDIR).Shapes.TallFilm.Film24\
 $(RDIR).Shapes.TallFilm.Film16\
 $(RDIR).Shapes.TallFilm.Film8\
 $(RDIR).Shapes.TallFilm.Film0
# If you think I'm going to add all the crap for the new Bounce,Film,FilmB
# and ZoomUp files, just to provide dependency, you are sadly mistaken

FILESS16=\
 ${RDIR}.Sound16.adpcm.Info \
 ${RDIR}.Sound16.adpcm.play \
 ${RDIR}.Sound16.adpcm.playx2 \
 ${RDIR}.Sound16.SoundE8 \
 ${RDIR}.Sound16.SoundE8x2 \
 ${RDIR}.Sound16.SoundS16 \
 ${RDIR}.Sound16.SoundS16x2 \
 ${RDIR}.Sound16.SoundS8 \
 ${RDIR}.Sound16.SoundS8x2 \
 ${RDIR}.Sound16.SoundU16 \
 ${RDIR}.Sound16.SoundU16x2 \
 ${RDIR}.Sound16.SoundU8 \
 ${RDIR}.Sound16.SoundU8x2

#
# GENERIC RULES
#                  
all: $(FILES) $(FILESDC) $(FILESTOOLS) $(FILESML) $(FILES3) ${FILES16}
          @echo $(COMPONENT): all build complete

install: $(FILES) $(FILESDC) $(FILESTOOLS) $(FILESML) $(FILES3) ${FILES16}
         |
         $(MKDIR) $(INSTDIR)
         |
         ${CP} $(RDIR).!Boot      ${INSTDIR}.!Boot      ${CPFLAGS}
         ${CP} $(LDIR).!Help      ${INSTDIR}.!Help      ${CPFLAGS}
         ${CP} $(RDIR).!Run       ${INSTDIR}.!Run       ${CPFLAGS}
         ${CP} $(RDIR).!Sprites   ${INSTDIR}.!Sprites   ${CPFLAGS}
         ${CP} $(RDIR).!Sprites22 ${INSTDIR}.!Sprites22 ${CPFLAGS}
         ${CP} $(RDIR).Access     ${INSTDIR}.Access     ${CPFLAGS}
         ${CP} $(RDIR).Default    ${INSTDIR}.Default    ${CPFLAGS}
         ${CP} $(LDIR).Messages   ${INSTDIR}.Messages   ${CPFLAGS}
         ${CP} $(RDIR).Player     ${INSTDIR}.Player     ${CPFLAGS}
         ${CP} $(RDIR).Sprites    ${INSTDIR}.Sprites    ${CPFLAGS}
         ${CP} $(RDIR).Sprites22  ${INSTDIR}.Sprites22  ${CPFLAGS}
         ${CP} $(RDIR).SetSndDir  ${INSTDIR}.SetSndDir  ${CPFLAGS}
         |
         ${CP} ${RDIR}.Decomp2    ${INSTDIR}.Decomp2    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp3    ${INSTDIR}.Decomp3    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp4    ${INSTDIR}.Decomp4    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp5    ${INSTDIR}.Decomp5    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp6    ${INSTDIR}.Decomp6    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp7    ${INSTDIR}.Decomp7    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp8    ${INSTDIR}.Decomp8    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp9    ${INSTDIR}.Decomp9    ${CPFLAGS}
         ${CP} ${RDIR}.Decomp17   ${INSTDIR}.Decomp17   ${CPFLAGS}
         ${CP} ${RDIR}.Documents  ${INSTDIR}.Documents  ${CPFLAGS}
         ${CP} ${RDIR}.MovingLine ${INSTDIR}.MovingLine ${CPFLAGS}
         ${CP} ${RDIR}.Shapes     ${INSTDIR}.Shapes     ${CPFLAGS}
         ${CP} ${RDIR}.Sound16    ${INSTDIR}.Sound16    ${CPFLAGS}
         ${CP} ${RDIR}.Tools      ${INSTDIR}.Tools      ${CPFLAGS}
         ${CP} ${RDIR}.Trajectory ${INSTDIR}.Trajectory ${CPFLAGS}
         |
         ${ATTR} -directories +wr ${INSTDIR}
         ${ATTR} -files +ol +or -ow +wr -ww ${INSTDIR}
         |
         @echo $(COMPONENT): installed

clean:
         $(RM) crunched.Player
         $(RM) $(RDIR).Player
         $(RM) $(RDIR).Decomp2.DecompresH
         $(RM) $(RDIR).Decomp2.Decompress
         $(RM) $(RDIR).Decomp3.DecompresH
         $(RM) $(RDIR).Decomp3.Decompress
         $(RM) $(RDIR).Decomp4.DecompresH
         $(RM) $(RDIR).Decomp4.Decompress
         $(RM) $(RDIR).Decomp5.DecompresH
         $(RM) $(RDIR).Decomp5.Decompress
         $(RM) $(RDIR).Decomp6.DecompresH
         $(RM) $(RDIR).Decomp6.Decompress
         $(RM) $(RDIR).Decomp8.Decomp24
         $(RM) $(RDIR).Decomp8.DecompresH
         $(RM) $(RDIR).Decomp8.Decompress
         $(RM) $(RDIR).Decomp9.Decomp24
         $(RM) $(RDIR).Decomp9.DecompresH
         $(RM) $(RDIR).Decomp9.Decompress
         $(RM) $(RDIR).MovingLine.Decompress
         @echo $(RDIR): cleaned

#
# Static dependencies:
#
$(RDIR).Player: crunched.Player
        ${SQUISH} ${SQFLAGS} -from crunched.Player -to $@

crunched.Player: bas.Player
        crunch.Player; BASIC

$(RDIR).Decomp2.Decompress $(RDIR).Decomp2.DecompresH: $(RDIR).Decomp2.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp2.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp3.Decompress $(RDIR).Decomp3.DecompresH: $(RDIR).Decomp3.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp3.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp4.Decompress $(RDIR).Decomp4.DecompresH: $(RDIR).Decomp4.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp4.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp5.Decompress $(RDIR).Decomp5.DecompresH: $(RDIR).Decomp5.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp5.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp6.Decompress $(RDIR).Decomp6.DecompresH: $(RDIR).Decomp6.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp6.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp8.Decomp24 $(RDIR).Decomp8.Decompress $(RDIR).Decomp8.DecompresH: $(RDIR).Decomp8.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp8.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).Decomp9.Decomp24 $(RDIR).Decomp9.Decompress $(RDIR).Decomp9.DecompresH: $(RDIR).Decomp9.MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /$(RDIR).Decomp9.MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).MovingLine.Decompress: MakeDecomp
        Set ARMovie$Dir $(RDIR)
        Set Basic$Crunch .
        /MakeDecomp
        Unset Basic$Crunch
        Unset ARMovie$Dir

$(RDIR).MovingLine.16yuv: Make16yuv
        Dir $(RDIR).MovingLine
        /^.^.Make16yuv
        Up 2

$(RDIR).MovingLine.8rgb11: Make8ict11
        Dir $(RDIR).MovingLine
        /^.^.Make8ict11
        Rename 8ict11 8rgb11
        Up 2

$(RDIR).MovingLine.8rgb22: Make8ict22
        Dir $(RDIR).MovingLine
        /^.^.Make8ict22
        Rename 8ict22 8rgb22
        Up 2

$(RDIR).MovingLine.8yuv11: Make8yuv11
        Dir $(RDIR).MovingLine
        /^.^.Make8yuv11
        Up 2

$(RDIR).MovingLine.8yuv22: Make8yuv22
        Dir $(RDIR).MovingLine
        /^.^.Make8yuv22
        Up 2

#---------------------------------------------------------------------------
# Dynamic dependencies:
