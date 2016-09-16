# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.17.90+28+g9f18016
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2 itstool git)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
_commit=9f1801698d9f4b6ccd8a20ed0e3d053f5e2f60ac
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
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
  make
}

package() {
  cd $pkgname
  make DESTDIR="$pkgdir" install
}
