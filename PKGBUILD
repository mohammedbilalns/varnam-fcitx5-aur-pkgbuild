# Maintainer: Mohammed Bilal <bilalnsmuhammed@gmail.com>
_name=varnam-fcitx5
pkgname="${_name}-git"
pkgver=r6.de41a96
pkgrel=1
pkgdesc="Fcitx5 wrapper for Varnam input method"
arch=('x86_64')
url="https://www.varnamproject.com/"
license=('Custom')
makedepends=( 'git' 'meson')
source=("git+https://github.com/varnamproject/varnam-fcitx5.git")
sha256sums=('SKIP')
depends=('fcitx5' 'fcitx5-configtool' 'govarnam' 'govarnam-schemes')
provides=('varnam-fcitx5')

pkgver() {
  cd ${_name}
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd ${_name}
  meson setup builddir 
  cd builddir 
  meson compile 
 
}

package() {
  cd ${_name}/builddir 
  DESTDIR=${pkgdir} meson install   
}

