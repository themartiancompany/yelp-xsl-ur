# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.19.90
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2 itstool)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(https://download.gnome.org/sources/$pkgname/${pkgver:0:4}/$pkgname-$pkgver.tar.xz)
sha256sums=('060706410bf9ec1b8d2c7c873482d11c71db18c3d1df544fe6556a45134e7bf6')

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
