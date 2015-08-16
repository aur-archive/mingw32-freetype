# Maintainer: Mikael Eriksson <mikael_miffe_eriksson@yahoo.se>

pkgname=mingw32-freetype
pkgver=2.5.3
pkgrel=1
pkgdesc="TrueType font rendering library (mingw32)"
arch=('any')
url="http://www.freetype.org/"
license=('GPL')
depends=(mingw32-runtime mingw32-zlib)
makedepends=(mingw32-gcc)
source=(http://download.savannah.gnu.org/releases/freetype/freetype-$pkgver.tar.gz)
options=(!strip !buildflags staticlibs)
md5sums=('cafe9f210e45360279c730d27bf071e9')

build() {
  cd "$srcdir/freetype-$pkgver"

  CC=i486-mingw32-gcc \
  ./configure --host=i486-mingw32 \
  --prefix=/usr/i486-mingw32 \
  --enable-static \
  --enable-shared \
  --with-zlib=/usr/i486-mingw32 \
  --without-png

  make
}

package() {
  cd "$srcdir/freetype-$pkgver"

  make DESTDIR="$pkgdir" install
}

# vim:set ts=2 sw=2 et:
