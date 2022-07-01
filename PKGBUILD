# Maintainer: Martin Sandsmark <martin.sandsmark@kde.org>
pkgname=seadrive-daemon-git
pkgver=r25.07a788a
pkgrel=1
pkgdesc="Daemon part of seadrive"
arch=(x86_64)
url="https://github.com/haiwen/seadrive-fuse"
license=(Apache)
depends=(libsearpc libcurl-compat libevent-compat openssl-1.0 fuse2)
makedepends=(git autoconf automake make gcc)
provides=(seadrive-daemon)
conflicts=(seadrive-daemon)
source=('git+https://github.com/haiwen/seadrive-fuse.git')
md5sums=('SKIP')

pkgver() {
    cd seadrive-fuse
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

# prepare() { }

build() {
	cd "${srcdir}/seadrive-fuse"
	./autogen.sh
	./configure --prefix=/usr
    make
}

package() {
	cd "${srcdir}/seadrive-fuse"
	make DESTDIR="$pkgdir" install
}
