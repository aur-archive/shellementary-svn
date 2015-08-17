# Maintainer: Doug Newgard <scimmia22 at outlook dot com>
# Contributor: twa022 <twa022 at gmail dot com>

pkgname=shellementary-svn
_pkgname=shellementary
pkgver=83648
pkgrel=2
pkgdesc="Zenity replacement based on EFL"
arch=('i686' 'x86_64')
url="http://www.enlightenment.org"
license=('MIT')
depends=('elementary')
makedepends=('subversion')
source=("svn+http://svn.enlightenment.org/svn/e/trunk/PROTO/$_pkgname")
md5sums=('SKIP')

pkgver() {
  cd "$SRCDEST/$_pkgname"

  LC_ALL=C svn info | awk '/Last Changed Rev/ {print $4}'
}

build() {
  cd "$srcdir/$_pkgname"

  ./autogen.sh --prefix=/usr
  
  make
}

package() {
  cd "$srcdir/$_pkgname"
  
  make DESTDIR="$pkgdir" install

# install license files
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
}
