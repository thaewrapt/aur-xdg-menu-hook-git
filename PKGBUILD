# $Id$
# Maintainer: Alexey Ugnichev <alexey.ugnichev@gmail.com>

_pkgname=xdg-menu-hook
_prefix=/usr/share/libalpm/hooks
pkgname=${_pkgname}-git
pkgver=1.0
pkgrel=1
pkgdesc='xdg-menu pacman hook, intended for regeneration of lightweight WM menus easily (git version)'
url='https://github.com/thaewrapt/xdg-menu-hook'
license=('GPL')
arch=('any')
depends=(
  'archlinux-xdg-menu'
)
makedepends=()
backup=()
conflicts=()
provides=()
source=("${_pkgname}::git+https://github.com/thaewrapt/xdg-menu-hook.git")
sha256sums=('SKIP')

pkgver() {
  cd "${srcdir}/${_pkgname}"

  # There [most probably] would not be a lot of versions upstream, otherwise we should migrate to tag-based version flow 
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "${srcdir}/${_pkgname}"

  HOOKSDIR="${pkgdir}${_prefix}/"
  
  install -Dm644 --target-directory "${HOOKSDIR}" *.hook
}

