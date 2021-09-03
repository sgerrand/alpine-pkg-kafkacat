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
source="kcat-$pkgver.tar.gz::https://github.com/edenhill/kcat/archive/$pkgver.tar.gz"
builddir="$srcdir/kcat-$pkgver"

build() {
	cd "$builddir"
	./configure \
		--prefix=/usr \
		--mandir=/usr/share/man \
		--enable-json
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

sha512sums="3d92666e61d8fca52be985c87b984c2b50ef6eabf3dce37b551d6f9988582dc22d5d3a18ac8932905d131af9ccfa38e886eefeed5a71ae828f5c4e0c77adf2d5  kcat-1.6.0.tar.gz"
