pkgname=lemonbar-ml-git
_pkgname=bar
pkgver=273.d5d2df4
pkgrel=1
pkgdesc="A lightweight xcb based bar with ported xft and multiline support."
arch=('i686' 'x86_64')
url="https://github.com/ibhagwan/bar"
license=('MIT')
depends=('libxcb' 'libxft' 'libx11')
makedepends=('git')
provides=('bar-aint-recursive' 'lemonbar')
conflicts=('bar-aint-recursive' 'lemonbar')
source=("$_pkgname::git+https://github.com/ibhagwan/bar.git#branch=xft-port")
sha256sums=('SKIP')

pkgver() {
  cd "$srcdir/$_pkgname"
  echo $(git rev-list --count xft-port).$(git rev-parse --short xft-port)
}

build() {
  cd "$srcdir/$_pkgname"
  make
}

package() {
  cd "$srcdir/$_pkgname"
  make PREFIX=/usr DESTDIR="$pkgdir" install
  install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
