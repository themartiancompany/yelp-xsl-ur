# Maintainer: Jan "heftig" Steffens <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=2.91.90
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.bz2)
sha256sums=('9a0447d7fb74232f9aba4a8ae09f2fac723024cb7a1f4c811cfac0ee452ece15')

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
