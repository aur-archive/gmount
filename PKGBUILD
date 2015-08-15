# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Christoph Zeiler <archNOSPAM_at_moonblade.dot.org>

pkgname=gmount
pkgver=0.1.1
pkgrel=3
pkgdesc="A GTK GUI for mounting disk images"
arch=('any')
url="http://gmount.sourceforge.net/"
license=('GPL')
source=(http://downloads.sourceforge.net/gmount/gmount-src-$pkgver.tar.bz2
        Makefile)
depends=('gtk-sharp-2')
md5sums=('cb7dd733c0f8d1a2b31840132554c93d'
         'd66b10b1d1e0f132b38ca3d77c8ece17')

build() {
  cd "$srcdir"/$pkgname/$pkgname

  install -Dm644 "$srcdir"/Makefile "$srcdir"/$pkgname/$pkgname

  export MONO_SHARED_DIR="$(pwd)"

  make
}

package() {
  cd "$srcdir"/$pkgname/$pkgname

  export MONO_SHARED_DIR="$(pwd)"

  make DESTDIR="$pkgdir" install
}
