(
   
    if [ $SUIDINSTALL == "y" ]; then
      MAKE_INSTALL="make suidinstall"
    else
      MAKE_INSTALL="make install"
    fi &&

    ./configure --prefix=/usr              \
                --build=$BUILD             \
                --sysconfdir=/etc/kismet   \
                --mandir=/usr/share/man    \
                --infodir=/usr/share/info  \
                --datadir=/usr/share       \
                --localstatedir=/var       \
                 $OPTS                    &&
    make dep                              && 
    make                                  &&
    prepare_install                       &&
    $MAKE_INSTALL

) > $C_FIFO 2>&1
