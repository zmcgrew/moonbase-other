if in_depends $MODULE libX11; then
  sedit 's:/\* #define X11_GRAPHICS \*/:#define X11_GRAPHICS:' include/config.h &&
  sedit 's:^WINX11LIB = -lXaw -lXmu -lXext -lXt -lX11:WINX11LIB = -lXaw -lXmu -lXext -lXt -lXpm -lX11:' sys/unix/Makefile.src &&
  sedit 's:^# WINSRC = $(WINTTYSRC):WINSRC = $(WINTTYSRC) $(WINX11SRC):' sys/unix/Makefile.src &&
  sedit 's:^WINOBJ = $(WINTTYOBJ):WINOBJ = $(WINTTYOBJ) $(WINX11OBJ):' sys/unix/Makefile.src &&
  sedit 's:^# LFLAGS = -L/usr/X11R6/lib:LFLAGS = -L/usr/X11R6/lib:' sys/unix/Makefile.src &&
  sedit 's:^WINLIB = $(WINTTYLIB):WINLIB = $(WINTTYLIB) $(WINX11LIB):' sys/unix/Makefile.src
fi &&

if in_depends $MODULE libXpm; then
  sedit 's:/\* #define USE_XPM \*/:#define USE_XPM:' include/config.h
fi &&

sedit 's:/^#define COMPRESS.*$:#define COMPRESS "/bin/gzip":'               include/config.h &&
sedit 's:/^#define COMPRESS_EXTENSION.*$:#define COMPRESS_EXTENSION ".gz":'  include/config.h &&
sedit 's:/\* #define DLB \*/:#define DLB:'                                     include/config.h &&
sedit 's:/\* #define AUTOPICKUP_EXTENSIONS \*/:#define AUTOPICKUP_EXTENSIONS:' include/config.h &&

sedit 's:/\* #define LINUX \*/:#define LINUX:'             include/unixconf.h &&
sedit 's:/\* #define TIMED_DELAY \*/:#define TIMED_DELAY:' include/unixconf.h &&

sedit 's:^# CC = gcc *$:CC = gcc:'  sys/unix/Makefile.src &&
sedit 's:^WINTTYLIB = -ltermlib:WINTTYLIB = -lncurses:' sys/unix/Makefile.src &&

sedit 's:^# CC = gcc *$:CC = gcc:' sys/unix/Makefile.utl &&
sedit 's:^# FLAGS = -L/sr/X11R6/lib:LFLAGS = -L/usr/X11R6/lib:' sys/unix/Makefile.utl &&
sedit 's:^YACC *= yacc:YACC = bison -y:' sys/unix/Makefile.utl &&
sedit 's:^LEX *= lex:LEX = flex:' sys/unix/Makefile.utl &&

sedit 's:^GAMEGRP *= bin:GAMEGRP = games:' sys/unix/Makefile.top &&
sedit 's:^GAMEPERM = 04755:GAMEPERM = 02755:' sys/unix/Makefile.top &&
sedit 's:^FILEPERM = 0644:FILEPERM = 0664:' sys/unix/Makefile.top &&
sedit 's:^DIRPERM = 0755:DIRPERM = 0775:' sys/unix/Makefile.top &&
sedit 's:^VERDATND =.*$:VARDATND = x11tiles NetHack.ad pet_mark.xbm rip.xpm:' sys/unix/Makefile.top &&

sh sys/unix/setup.sh &&

default_make &&
chmod 0775 /usr/games/lib/nethackdir
