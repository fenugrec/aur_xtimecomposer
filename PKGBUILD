# Maintainer: Will Price <will.price94+aur@gmail.com>

# note : download needs to be via web + login

pkgname=xtimecomposer
pkgver=15.2.1
pkgrel=1
pkgdesc="Eclipse based IDE for the xCORE microcontrollers"
arch=('x86_64' 'i686')
url="https://www.xmos.ai/software-tools/"
license=('Custom')
provides=('xtimecomposer')
requires=('ncurses5-compat-libs')
options=(!strip)

source=("Tools-15---Linux-64_${pkgver}.tgz::https://www.xmos.ai/file/tools-15-linux-64?version=latest")
sha256sums=('e39738a46fb001afcdcb78e37c95276b826abd8fd08140d25e678325b6410189')


# Don't compress as it takes forever!
PKGEXT=".tar"

prepare() {
# create profile script that appends to PATH
	cat > ${pkgname}.sh <<END
export PATH="\$PATH":'/opt/XTC/${pkgver}/bin'
END
}

package() {
	install -Dm644 ${pkgname}.sh "$pkgdir/etc/profile.d/${pkgname}.sh"
	install -d -m755 "${pkgdir}/opt"
	install -d -m755 "${pkgdir}/usr/bin/"
	cp -r "$srcdir/XMOS/XTC" "${pkgdir}/opt/"
}
