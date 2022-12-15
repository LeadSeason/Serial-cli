pkgname="Serial-cli-git"
_pkgname="Serial-cli"
pkgver=1.0.0.r0.60c08d8
pkgrel=1
pkgdesc="serial app"
arch=('x86_64' 'x86')
url="https://github.com/ToniLipponen/Serial-cli.git"
license=('MIT')
makedepends=(
	'git'
	'gcc'
)
source=("${_pkgname}::git+https://github.com/ToniLipponen/Serial-cli.git")
sha512sums=("SKIP")
provides=(serial-cli)

build() {
	cd "${srcdir}/${_pkgname}"
	make build
}

package() {
	cd "${srcdir}/${_pkgname}"
	echo pkgdir: $pkgdir
	echo srcdir: $srcdir
	pwd
	ls
	make install DESTDIR="$pkgdir" PREFIX="/usr"
	install -Dm644 LICENSE -t "${pkgdir}/usr/share/licenses/${_pkgname}"
}
