source /etc/profile.d/qt6.rc &&
#Detected locale "en_US" with character encoding "ISO-8859-1", which is not UTF-8.
#Qt depends on a UTF-8 locale, and has switched to "en_US.UTF-8" instead.
export LANG='en_US.UTF-8'

OPTS+=" -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DKDE_INSTALL_USE_QT_SYS_PATHS=ON \
        -DKDSingleApplication_QT6=ON"

default_cmake_build
