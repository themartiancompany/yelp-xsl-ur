# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2025  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Maintainer: Truocolo <truocolo@aol.com>
# Maintainer: Truocolo <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
# Maintainer: Pellegrino Prevete (dvorak) <pellegrinoprevete@gmail.com>
# Maintainer: Pellegrino Prevete (dvorak) <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Maintainer: Jan Alexander Steffens (heftig) <heftig@archlinux.org>

_proj="gnome"
_pkg="yelp"
pkgname="${_pkg}-xsl"
pkgver=42.1
pkgrel=2
pkgdesc="Document transformations from Yelp"
_http="https://gitlab.${_proj}.org"
_ns="GNOME"
url="${_http}/${_ns}/${pkgname}"
arch=(
  'any'
)
license=(
  'GPL'
)
makedepends=(
  'autoconf'
  'itstool'
  'git'
  'which'
)
_commit="1658a8eb59a296d9e7b7116fbc79ca778b702e14"  # tags/42.1^0
source=(
  "git+${url}.git#commit=${_commit}"
)
sha256sums=(
  'SKIP'
)

pkgver() {
  cd \
    "${pkgname}"
  git \
    describe \
    --tags | \
    sed \
      's/[^-]*-g/r&/;s/-/+/g'
}

prepare() {
  cd \
    "${pkgname}"
  NOCONFIGURE=1 \
  ./autogen.sh
}

build() {
  cd \
    "${pkgname}"
  ./configure \
    --prefix="/usr" \
    --sysconfdir="/etc" \
    --localstatedir="/var"
  make
}

package() {
  cd \
    "${pkgname}"
  make \
    DESTDIR="${pkgdir}" \
    install
}

# vim:set sw=2 sts=-1 et:
