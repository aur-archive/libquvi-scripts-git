# Contributor: Gustavo Alvarez <sl1pkn07@gmail.com>

pkgname=libquvi-scripts-git
pkgver=v0.9.20131130.0.ga5f5e79
pkgrel=1
pkgdesc="Embedded lua scripts for libquvi. (GIT version)"
arch=('any')
url="http://quvi.sourceforge.net/"
license=('AGPL3')
depends=('lua-socket' 'lua-expat' 'lua-bitop' 'lua-luajson')
makedepends=('git' 'asciidoc')
options=('!libtool')
provides=('libquvi-scripts')
conflicts=('libquvi-scripts')
source=('git://repo.or.cz/libquvi-scripts.git#branch=next')
_gitname="libquvi-scripts"
sha256sums=('SKIP')

pkgver() {
  cd "${_gitname}"
  echo "$(git describe --long --tags | tr - .)"
}

build() {
  cd "${_gitname}"

  ./bootstrap.sh

  ./configure --prefix=/usr --with-nsfw --with-geoblocked

  make
}

package() {
  cd "${_gitname}"

  make DESTDIR="$pkgdir" install
}

