# Original Maintainer: Jakub Klinkovský <j.l.k@gmx.com>
# Maintainer: Bernd Busse <bernd AT bussenet DOT de>

pkgname=sxlock-git
_pkgname=sxlock
pkgver=v1.1.6.g8501e13
pkgrel=1
pkgdesc="Simple screen locker utility for X, fork of sflock. Uses PAM authentication, no suid needed."
arch=('i686' 'x86_64')
url="https://github.com/tryone144/sxlock"
license=('MIT')
depends=('libxext' 'libxrandr' 'pam')
makedepends=('git')
source=('git://github.com/tryone144/sxlock.git')
md5sums=('SKIP')

pkgver() {
  cd "$_pkgname"
  git describe --always | sed 's|-|.|g'
}

build() {
  cd "$_pkgname"
  make
}

package() {
  cd "$_pkgname"
  make DESTDIR="$pkgdir" install
  chmod 4755 "$pkgdir/usr/bin/sxlock"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}

# vim:set ts=2 sw=2 et:
