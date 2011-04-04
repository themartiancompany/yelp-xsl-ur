# Maintainer: Jan "heftig" Steffens <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.0.0
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.bz2)
sha256sums=('60d62ad2f747e5f7564be5d4e7d014164b1951dc7aa9f65cd4c2c6150ea5d8e3')

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
