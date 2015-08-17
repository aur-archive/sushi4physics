# Maintainer: Gustavo Castro << gustawho [at] gmail [dot] com >>
pkgname=sushi4physics
_srcname=SusHi
pkgver=1.4.1
pkgrel=2
pkgdesc="Higgs production in the MSSM and the 2HDM - Standalone"
url="http://sushi.hepforge.org/"
arch=('x86_64')
license=('GPLv2')
depends=('lhapdf')
makedepends=('gcc-fortran')
provides=('sushi4physics')
conflicts=('sushi4physics-2hdmc' 'sushi4physics-fh' 'sushi4physics-hb')
source=("http://www.hepforge.org/archive/sushi/${_srcname}-${pkgver}.tar.gz")
sha512sums=('3033c35551fc6ba50afef00cf7facccbae7c82b63f90df293167e7318e35576ef6033b94b68ce6330d43b4c61416e5d5589a118c6b7389cf2ba96c0148e0c5ff')

build() {
  cd "${srcdir}/${_srcname}-${pkgver}"
  ./configure --prefix=/usr
  make
}

package() {
  mkdir -p "${pkgdir}/usr/bin" "${pkgdir}/usr/lib"
  cd "${srcdir}/${_srcname}-${pkgver}"
  install -m755 bin/sushi.PLAIN "${pkgdir}/usr/bin/sushi.PLAIN"
  install -m755 lib/libshare.a "${pkgdir}/usr/lib/libshare.a"
  install -m755 lib/libsushiPLAIN.a "${pkgdir}/usr/lib/libsushiPLAIN.a"
  ln -s "${pkgdir}/usr/bin/sushi.PLAIN" "${pkgdir}/usr/bin/sushi"
  ln -s "${pkgdir}/usr/lib/libsushiPLAIN.a" "${pkgdir}/usr/lib/libsushi.a"
}

# vim:set ts=2 sw=2 et:
