pkgname=libgtop
pkgver=2.40.0
pkgrel=1
pkgdesc="A library that reads information about processes and the running system"
arch=('x86_64')
license=('LGPL')
depends=('glib2' 'libxau')
makedepends=('gobject-introspection')
install=libgtop.install
source=(http://ftp.gnome.org/pub/gnome/sources/${pkgname}/${pkgver:0:4}/${pkgname}-${pkgver}.tar.xz)
url="http://www.gnome.org/"
sha256sums=('78f3274c0c79c434c03655c1b35edf7b95ec0421430897fb1345a98a265ed2d4')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  ./configure --prefix=/usr --sysconfdir=/etc \
      --localstatedir=/var --disable-static \
      --with-libgtop-smp
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"
  make DESTDIR="${pkgdir}" install
}
