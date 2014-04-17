# Maintainer: Sung Pae <self@sungpae.com>
pkgname=isync
pkgver=1_1_0.35.g64a6596
pkgrel=1
pkgdesc="Sung Pae's isync/mbsync build"
arch=('x86_64')
url="https://github.com/guns/rxvt-unicode"
license=('GPL')
groups=('guns')
depends=('openssl')
makedepends=('git')
provides=('isync' 'mbsync')
conflicts=('isync' 'mbsync')

pkgver() {
    printf %s "$(git describe --long --tags | tr - .)" | sed 's/^isync_//'
}

build() {
    cd "$startdir"
    ./autogen.sh
    ./configure --prefix /usr
    make -j $(grep -c ^processor /proc/cpuinfo)
}

package() {
    cd "$startdir"
    make DESTDIR="$pkgdir/" install
}
