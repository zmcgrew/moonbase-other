(

#  sedit 's;install-meta:: $(ObjDir)/META.llvm;install-meta:: META.llvm;' bindings/ocaml/llvm/Makefile &&

  sedit 's:/docs/llvm:/share/doc/llvm:' Makefile.config.in &&

  OPTS+=" --enable-shared --enable-targets=host-only" &&

  default_build

) > $C_FIFO 2>&1
