(

  sedit "s:#undef _XOPEN_SOURCE::" config.h.in  &&
  sedit "s:\$(DESTDIR)\$(icondir):/usr/share/pixmaps:" icons/Makefile.in  &&
  sedit "s:\$(DESTDIR)\$(applicationdir):/usr/share/applications:" icons/Makefile.in  &&

  default_game_build

) > $C_FIFO 2>&1
