(

  # fix swig generation with current ocaml
  sedit "3364 s:\(^.*$\):\1; sed -i \"/int caml_array_length/ d\" gv_ocaml.cpp:" tclpkg/gv/Makefile.in &&

# This line takes care of the cannot find libperl.so rebuild that
# happens on a lunar fix.
  PERL_MAJ_VER="`lvu version perl |cut -c 1`" &&
  PERL_VER="`lvu version perl`" &&
  PERL_SO_PATH="/usr/lib/perl$PERL_MAJ_VER/$PERL_VER/`arch`-linux-thread-multi/CORE/" &&
# If you have R installed you will get the same type rebuild kick off because
# libR.so cannot be found.
  R_SO_PATH="/usr/lib/R/lib " &&
# So lets put all that together.
  LDFLAGS="$LDFLAGS -Wl,-rpath,${PERL_SO_PATH},-rpath,${R_SO_PATH}" &&
# done

  OPTS+=" --with-libgd --with-fontconfig" &&

  default_build &&

  # create the default config-files
  dot -c

) > $C_FIFO 2>&1
