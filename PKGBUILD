# Maintainer: Matt C <matt[at]getcryst[dot]al>
pkgname=libpamac
pkgver=11.3.0
pkgrel=1
pkgdesc="Library for Pamac"
arch=('x86_64')
url="https://gitlab.manjaro.org/applications/libpamac"
depends=('flatpak')
makedepends=('clang' 'ninja' 'cmake' 'git' 'unzip' 'meson' 'gobject-introspection')

source=("libpamac::git+${url}.git")
sha256sums=('SKIP')

build() {
    cd ${srcdir}/libpamac
    mkdir build
    cd build
    meson setup --prefix=${pkgdir}/usr --sysconfdir=${pkgdir}/etc -Denable-flatpak=true --buildtype=release
    meson compile
    
}

package() {
    OLD=$(pwd)
    cd ${srcdir}/libpamac/build
    meson install
    cd $OLD
    rm -rfv pkg src libpamac/
}
