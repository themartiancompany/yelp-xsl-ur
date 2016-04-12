# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.20.1
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2 itstool)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(https://download.gnome.org/sources/$pkgname/${pkgver:0:4}/$pkgname-$pkgver.tar.xz)
sha256sums=('dc61849e5dca473573d32e28c6c4e3cf9c1b6afe241f8c26e29539c415f97ba0')

build() {
  cd $pkgname-$pkgver
  rm xslt/common/domains/yelp-xsl.xml
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
