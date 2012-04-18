# Maintainer: Jan Alexander Steffens (heftig) <jan.steffens@gmail.com>

pkgname=yelp-xsl
pkgver=3.4.1
pkgrel=1
pkgdesc="Stylesheets for Yelp"
arch=(any)
makedepends=(intltool libxslt libxml2 itstool)
license=(GPL)
options=('!emptydirs')
url="http://www.gnome.org"
source=(http://ftp.gnome.org/pub/gnome/sources/$pkgname/${pkgver%.*}/$pkgname-$pkgver.tar.xz)
sha256sums=('f667b26dca7b9e09fb6855d0626a003adc102dcbf59c3a2c37ac9aefe1d6c867')

build() {
  cd $pkgname-$pkgver
  ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
  make
}

package() {
  cd $pkgname-$pkgver
  make DESTDIR="$pkgdir" install
}
