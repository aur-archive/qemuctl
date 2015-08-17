# Maintainer: American_Jesus <american.jesus.pt AT gmail DOT .com>
# Contributor: Fackamato <mathias.buren.at.gmail.com>
pkgname=qemuctl
pkgver=0.3.0
pkgrel=2
pkgdesc="This is a controller GUI for the run-time options of QEMU computer emulator. It can be
used as a stand-alone application or as a plug-in for Qemu Launcher. (Only x86 PC emulator is
supported.)"
url="http://sourceforge.net/projects/qemuctl/"
license="GPL"
arch=(i686 x86_64)
depends=('qemu' 'qt4')
source=(http://sourceforge.net/projects/$pkgname/files/source/$pkgver/$pkgname$pkgver.tar.gz
        usleep.patch)
md5sums=('fac258292e966603f0679240482f7543'
         'a8b54f37b96bb3d743ff2511bb65f420')

build() {
  tar xf $pkgname$pkgver.tar.gz
  cd "$srcdir/$pkgname$pkgver"
  patch -p0 < $startdir/usleep.patch
        qmake-qt4
  make
        mkdir -p $startdir/pkg/usr/bin
        install -m 755 $pkgname $startdir/pkg/usr/bin
}
