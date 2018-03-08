# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.27.90+2+g72821085
pkgrel=1
pkgdesc="Document transformations from Yelp"
url="https://git.gnome.org/browse/yelp-xsl"
arch=(any)
license=(GPL)
makedepends=(intltool libxslt libxml2 itstool git)
_commit=72821085aef6667c468bcb03a22592d7d6214443  # master
source=("git+https://git.gnome.org/browse/yelp-xsl#commit=$_commit")
sha256sums=('SKIP')

pkgver() {
  cd $pkgname
  git describe --tags | sed 's/-/+/g'
}
prepare() {
  cd $pkgname
  NOCONFIGURE=1 ./autogen.sh
}

build() {
  cd $pkgname
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var \
    --enable-doc
  make
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir" install
}
