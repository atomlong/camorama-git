# Maintainer: Steffen Weber <-boenki-gmx-de->
# Contributor: Andrea Scarpino <bash.lnx@gmail.com>
# Contributor: Federico Quagliata (quaqo) <quaqo@despammed.com>

pkgname=camorama-git
pkgver=0.21.2_22_gc0ac70c
pkgrel=1
pkgdesc="GNOME 2 Webcam application featuring various image filters"
url="https://github.com/alessio/camorama"
arch=('i686' 'x86_64' 'arm' 'armv6h' 'armv7h' 'aarch64')
license=('GPL2')
depends=('libgnomeui')
makedepends=('git' 'intltool' 'gnome-common' 'libv4l')
conflicts=('camorama')
provides=('camorama')
source=(git+https://github.com/alessio/camorama.git)
sha512sums=('SKIP')

pkgver() {
  cd "${pkgname%-git}"
  git describe --tags --long | sed s/-/_/g
}

build() {
  cd "${pkgname%-git}"
  sh ./autogen.sh
  ./configure --prefix=/usr --sysconfdir=/usr/share
  make
}

check() {
  cd "${pkgname%-git}"
  make check
}

package() {
  cd "${pkgname%-git}"
  make DESTDIR="$pkgdir" install
}
