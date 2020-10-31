# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=kafkacat
pkgver=1.6.0
pkgrel=0
pkgdesc="Generic command line non-JVM Apache Kafka producer and consumer"
url="https://github.com/edenhill/kafkacat"
arch="all"
license="BSD-2-Clause-Patent"
depends="librdkafka yajl"
depends_dev=""
makedepends="$depends_dev bash librdkafka-dev musl-dev yajl-dev zlib-dev"
install=""
subpackages="$pkgname-dev $pkgname-doc"
source="kafkacat-$pkgver.tar.gz::https://github.com/edenhill/kafkacat/archive/$pkgver.tar.gz"
builddir="$srcdir/kafkacat-$pkgver"

build() {
	cd "$builddir"
	./configure \
		--build=$CBUILD \
		--host=$CHOST \
		--prefix=/usr \
		--sysconfdir=/etc \
		--mandir=/usr/share/man \
		--localstatedir=/var
	make
}

package() {
	cd "$builddir"
	make DESTDIR="$pkgdir" install
}

dev() {
	mkdir "$subpkgdir"
	default_dev
}

doc() {
	mkdir "$subpkgdir"
	default_doc
}

sha512sums="a203f3db21fef7b885d5b394458541c830078ae3fe4c8d2d59226db14db6ef470e167bd9491982751086cd96837ff10699709e4379d007857a4058335207e858  kafkacat-1.6.0.tar.gz"
