# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=kafkacat
pkgver=1.4.0
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

sha512sums="c4607ae16b693fa60ba51dec3ecd527197de56d91c7a2a6397d9f56af6db41bee9bf702943fb56f4ce7d6b996cd7eb7d86881b8a5002f3b450fa6f7485854690  kafkacat-1.4.0.tar.gz"
