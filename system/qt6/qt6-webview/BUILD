source /etc/profile.d/qt6.rc &&

#Generating .rcc/qmlcache/qtgraphicaleffectsplugin_ColorOverlay_qml.cpp
#Detected locale "en_US" with character encoding "ISO-8859-1", which is not UTF-8.
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

# This applies here as well; https://github.com/neovim/neovim/issues/2557
CFLAGS="-U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2"
CXXFLAGS="-U_FORTIFY_SOURCE -D_FORTIFY_SOURCE=2"

OPTS+=" -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$MODULE_PREFIX \
        -DINSTALL_LIBEXECDIR=qt6 \
        -DINSTALL_LIBDIR=qt6 \
        -DINSTALL_DOCDIR=share/doc/qt6 \
        -DINSTALL_ARCHDATADIR=qt6 \
        -DINSTALL_DATADIR=share/qt6 \
        -DINSTALL_INCLUDEDIR=include/qt6 \
        -DINSTALL_MKSPECSDIR=qt6/mkspecs \
        -DINSTALL_EXAMPLESDIR=share/doc/qt6/examples \
        -DCMAKE_MESSAGE_LOG_LEVEL=STATUS \
        -DINSTALL_SYSCONFDIR=/etc/xdg"

cmake -B $MODULE-$VERSION -S . -G Ninja $OPTS -Wno-dev &&
cmake --build $MODULE-$VERSION &&
prepare_install &&

# Remove point to the src build direcotry
find $MODULE-$VERSION -type f -name '*.prl' -exec sed -i -e '/^QMAKE_PRL_BUILD_DIR/d;s/\(QMAKE_PRL_LIBS =\).*/\1/' {} \; &&

cmake --install $MODULE-$VERSION
