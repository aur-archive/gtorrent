# Maintainer: nyanpasu~ <atago@pomf.se>

pkgname=gtorrent
# TODO Read pkgver somehow from the repo.
pkgver=0.0.1
pkgrel=3
pkgdesc='A minimalistic lightweight bittorrent client written by the 4chan technology board.'
arch=('i686' 'x86_64')
url="https://github.com/gtorrent/gTorrent"
license=('unknown')
depends=('boost' 'glibmm' 'gtkmm3' 'libtorrent-rasterbar')
makedepends=('cmake' 'git')
optdepends=()
provides=("${pkgname}")
conflicts=("${pkgname}")
source=("git://github.com/gtorrent/gTorrent.git")
md5sums=('SKIP')

build() {
    cd "$srcdir/gTorrent"
    mkdir -p build/
    cd build/
    cmake ..
    make PREFIX=/usr -j`nproc`
}

package() {
    cd "$srcdir/gTorrent/build"
    make PREFIX=/usr DESTDIR="$pkgdir" install
}
