# Contributor: Tux Tong <huntthetux@gmail.com>

pkgname=brother-dcpj100
_printername=dcpj100
pkgver=3.0.0
pkgrel=666
pkgdesc="CUPS driver for Brother DCP-J100 printer"
arch=('i686' 'x86_64')
license=('custom:Brother Industries')
depends=('cups' 'tcsh')
if [ "$CARCH" == "x86_64" ]; then
  depends+=('lib32-libstdc++5')
fi
makedepends=('rpmextract')
url="http://solutions.brother.com/linux/en_us/index.html"
source=(http://www.brother.com/pub/bsc/linux/dlf/${_printername}cupswrapper-$pkgver-1.i386.rpm \
	http://www.brother.com/pub/bsc/linux/dlf/${_printername}lpr-$pkgver-1.i386.rpm)
md5sums=('33486e8669dd77b0b88711d1b84218fd'
         'c5add66bcef0f7d95498c44d2c7ba68a')
install=dcpj100.install
package() {
   cd "$pkgdir"
   for n in $startdir/src/*.rpm; do
     rpmextract.sh "$n"
   done

   sed -i 's|/etc/init.d/cups|/etc/rc.d/cupsd|' "${pkgdir}/opt/brother/Printers/dcpj100/cupswrapper/cupswrapperdcpj100"
}

