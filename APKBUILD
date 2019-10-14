# Contributor: Sasha Gerrand <alpine-pkgs@sgerrand.com>
# Maintainer: Sasha Gerrand <alpine-pkgs@sgerrand.com>
pkgname=kafkacat
pkgver=1.5.0
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

sha512sums="57f75b26ef32df244043fa9fc17dc2d6fd93daeea4bc389aa78356ea6e45dea780ff9c3462ed27d2a7798560a21eef04f098bf7766c7305bcee4573f557651ad  kafkacat-1.5.0.tar.gz"
