# Maintainer: Case Duckworth <cased123@gmail.com>

pkgname=lemonbar-borders-git
_pkgname=bar
pkgver=255.da27d39
pkgrel=1
pkgdesc="A lightweight xcb based bar with xft and border support."
arch=('i686' 'x86_64')
url=https://github.com/duckwork/bar
license=('MIT') # I think
depends=('libxcb' 'libxft' 'libx11')
makedepends=('git')
provides=('bar-aint-recursive' 'lemonbar')
conflicts=('bar-aint-recursive' 'lemonbar')
source=("$_pkgname::git+https://github.com/duckwork/bar.git#branch=xft-port")
sha256sums=('SKIP')

pkgver() {
    cd "$srcdir/$_pkgname"
    echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
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
