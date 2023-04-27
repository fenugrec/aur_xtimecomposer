# Maintainer: Will Price <will.price94+aur@gmail.com>
pkgname=xtimecomposer
pkgver=14.4.1
pkgrel=1
pkgdesc="Eclipse based IDE for the xCORE microcontrollers"
arch=('x86_64' 'i686')
url="https://www.xmos.com/products/tools/xtimecomposer"
license=('Custom')
provides=('xtimecomposer')
options=(!strip staticlibs)
depends=(java-runtime)

source=("xTIMEcomposer-Community_${pkgver%%.*}-Linux64-Installer_Community_$pkgver.tgz::https://www.xmos.com/published/xtimecomposer-community_14-linux64-installer?ver=latest")
sha256sums=('1fa239dca4bff36b91a37b5d73264cd97967bec2d7456b2d5b2c1b660fd20b19')


# Don't compress as it takes forever!
PKGEXT=".tar"

prepare() {
    ln -s --force \
        /usr/lib/libpangoft2-1.0.so.0 \
        "$srcdir/XMOS/xTIMEcomposer/Community_${pkgver}/xtimecomposer_bin/swtbrowserlibs/"
}

package() {
    cd "$srcdir/XMOS/"
    mkdir -p "$pkgdir"/usr/{share,bin}
    cp -r xTIMEcomposer "$pkgdir/usr/share"
    cd "$pkgdir/usr/bin"
    ln -s /usr/share/xTIMEcomposer/Community_${pkgver}/bin/xtimecomposer .
}
