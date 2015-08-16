# Maintainer: Dominik Köppl <dominik@devwork.org>
# Contributor: Robert Schwarz <mail at rschwarz dot net>
pkgname=lemon-graphs
_pkgname=lemon
pkgver=1.3
pkgrel=1
pkgdesc="A C++ template library with focus on graphs"
arch=(i686 x86_64)
makedepends=('cmake') 
url="http://lemon.cs.elte.hu/trac/lemon"
license=('custom:BOOST')
source=(http://lemon.cs.elte.hu/pub/sources/$_pkgname-$pkgver.tar.gz)
md5sums=(814d97757c157c5b46a413cc39aad625)

build() {
  mkdir "$srcdir/$_pkgname-$pkgver-build" &&
  cd "$srcdir/$_pkgname-$pkgver-build"
  cmake -DCMAKE_INSTALL_PREFIX:PATH=/usr "$srcdir/$_pkgname-$pkgver" 
#  ./configure --prefix=/usr --disable-tools --without-glpk --without-cplex --without-soplex --without-coin CXX='g++' CXXFLAGS='-march=native -O3'
  make
}

package() {
  cd "$srcdir/$_pkgname-$pkgver-build"
  make DESTDIR="$pkgdir/" install
  install -D -m644 "$srcdir/$_pkgname-$pkgver/LICENSE" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}

# vim:set ts=2 sw=2 et:
