# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=kafkacat
pkgver=1.3.1
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

sha512sums="98e51c7ad4a3bb1eda8587af5e4d9ce164d26a9511470799a8379e89d2462397eb51e80ccde6a5c9240b99b014f7ca2c6d494a576de3e0be65df744ebc56d758  kafkacat-1.3.1.tar.gz"
