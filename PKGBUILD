# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.20.1
pkgrel=2
pkgdesc="Document transformations from Yelp"
url="https://git.gnome.org/browse/yelp-xsl"
arch=(any)
license=(GPL)
makedepends=(intltool libxslt libxml2 itstool git)
_commit=16ebea986edc8cc394a0e81350202be312e7aadf
source=("git://git.gnome.org/yelp-xsl#commit=$_commit")
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
