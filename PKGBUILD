# $Id$
# Maintainer: Andreas B. Wagner <AndreasBWagner@pointfree.net>
# Contributor: Sebastien Binet <binet@farnsworth>
pkgname=cblas
pkgver=3.3.0
pkgrel=3
pkgdesc="C interface to the BLAS"
url="http://www.netlib.org/blas"
arch=('i686' 'x86_64')
license=('custom')
depends=('glibc' 'blas')
makedepends=('gcc' 'gcc-fortran')
conflicts=()
replaces=()
backup=()
install=
source=(
  'http://www.netlib.org/blas/blast-forum/cblas.tgz' 
  'cblas.patch' 
  'Makefile.in'
  'LICENSE'
)

build() {
  cd $srcdir/CBLAS

  /bin/cp $srcdir/Makefile.in .
  patch -p0 < $srcdir/cblas.patch

  install -d $srcdir/CBLAS/src/lib

  install -d $pkgdir/usr/lib
  install -d $pkgdir/usr/include

  make alllib || return 1

  install -m755 $srcdir/CBLAS/src/lib/* $pkgdir/usr/lib
  install -m644 $srcdir/CBLAS/include/cblas.h $pkgdir/usr/include

  install -m755 -d $pkgdir/usr/share/licenses/cblas
  install -m644 $srcdir/LICENSE $pkgdir/usr/share/licenses/cblas/
}
md5sums=('1e8830f622d2112239a4a8a83b84209a'
         'e779fc195f8f48672656522bcfd642e4'
         'a4dc51bcd46f80b921be46f1fa855f00'
         '38b6acb8ed5691d25863319d30a8b365')
