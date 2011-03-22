# Maintainer: Jan "heftig" Steffens <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=2.91.92
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.bz2)
sha256sums=('ab3d26192cf4465f1dad187d975201767b45ca3dc908820fc0ee9924bca42175')

build() {
  cd "$srcdir/$pkgname-$pkgver"
  ./configure --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"
  make DESTDIR="$pkgdir" install
}
